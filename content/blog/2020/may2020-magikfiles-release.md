---
title: "Magikfiles version 1"
date: 2020-05-03
description: "MagikFiles V1 just released, here is the main achievements of the project..."
---

As you may know, I am the creator and developer of [MagikFiles](https://github.com/jaekr/magikfiles), a free, open-source and self-hosted file sharing software.  
The whole code is under the [MIT](https://opensource.org/licenses/MIT) license so everyone can reuse it personally or in a profesionnal setting.  

I started this project in February 2020, as a way to learn how to use NodeJS and Express and it quickly became the most active one I am currently working on.  
If I were to be honnest, I would say that I hate this project because it's made uniquely of Javascript and it is one of the languages I like the least but for the sake of this article, let's say everything is good and let's see how it works.  

First of all, in the beggining, I wanted Magikfiles to be compatible with ActiveDirectory so it could be used in a company more easily like you share a file, it detects automatically the current user, opens a popup with all the contacts and check the ones they want the file to be share with.  
I quickly abandonned this idea since I was too lazy to replicate a AD infrastructure on my own network and I think it would have been a mess to integrate properly.  

To manage the uploads, I used `express-fileupload`, a really simple library.  
Because I wanted to support multi file uploads as well as single file uploads, this small bit of code was my first achievement of the project:

```
let sampleFile = req.files.file;
// If the 'file' property is an array:
// Multiple upload
if (Array.isArray(sampleFile)) {
  sampleFile.forEach((element) => {
    element.mv(`${__dirname}/f/${fileUUID}/${element.name}`, function (err) {
      if (err) {
        return res.status(500).send(err);
      }
    });
  });
} else {
  // If the 'file' property is not an array:
  // Simple upload
  sampleFile.mv(`${__dirname}/f/${fileUUID}/${sampleFile.name}`, function (
   err
  ) {
    if (err) {
      return res.status(500).send(err);
    }
  });
}
```

When you upload multiple files, `express-fileupload` stores them in an array and I found out that the quickest way to detect if multiple files are uploaded, it is obviously to check if the send `file` is an array or not.  
As you may imagine, it works flawlessly so I kept this first portion of spaghetti code.  

My second achievement was on how to show a file or a folder to an end user.  
The code looks like this:

```
app.get("/f/:uuid", async (req, res, next) => {
  var getUUID = req.params.uuid;

  let files = [];
  let imgFormats = ["png", "jpg", "jpeg", "gif", "webm"];

  try {
    fs.readdirSync(`${__dirname}/f/${getUUID}/`).forEach((file) => {
      files.push(file);
    });
  } catch (e) {
    return res.redirect("/");
  }

  await redisClient.get(getUUID, function (err, response) {
    if (response != null) {
      return res.status(301).redirect(`/auth?g=${getUUID}`);
    } else {
      res.render("view", {
        files: files,
        curUUID: getUUID,
        imgFormats: imgFormats,
        hostname: process.env.HOSTNAME,
      });
    }
  });

});
```

To understand this code better, you first need to know how the file upload works.  
Here is how:
 1. At the start of the application, a folder named `f` is created (f for files), it will be where we will store our files
 2. A post request containing the files is made to the `/up` address, if the server detects no files or a file that is too big, it will throw an exception
 3. A random UUID is created and the `f` folder is checked to see if this UUID already exists, if it does (which is mostly improbable), it re-generates one, checks it and so on
 4. The server then checks if multiple files were uploaded, if so, it will also check the checksums of the files to see if the same file has been uploaded multiple times
 5. If everything is fine, the directory named after the UUID is created and the files are moved into it and then the server redirects the user to the folder page located at `/f/UUID`

After this, when the user makes a request to `/f/UUID`, the server will check in the `f` folder to first see if the UUID exists. Then, the server looks into the directory to see if there is files in it, in case the directory doesn't exists / is empty, the user will be redirected to the main page.  
The server then lists files, put them into and array and the page is displayed.  
Also, in case of a password, the server will redirect to a auth page.  
When displaying the page, the server will build up an array of image format that will be displayed in a `<img>` tag just so the page will be a little bit more fancier.  
It took me some time to make this system but at the end, I am satisfied with the result.  

My last achievement is the Docker integration.  
I think Docker makes it easy to deploy apps like theses and it was important for me that I would provide a quick and easy way to deploy my app.  


As now, here is the features of Magikfiles:
 - File upload (obiously)
 - Folder view
 - Share folder url
 - Share file url
 - Folders with password
 - Global file size limits

I am currently working on the next release that will implement codes in order to upload files.  
It will likely be the last release and after it, the repo will be archived.  

If you wish to help, the [repo is currently hosted on Github](https://github.com/jaekr/magikfiles).  

That's all for today.  
I'll see you next time!
