## Common mistake:Embedding git repositories


![github embedding.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1656934365537/h5ldJHbXC.PNG align="left")


If you have encountered the above warning while pushing your code to the github,then you are at the right place!


This warning occurs when there is git repository inside another git repository.

Most commonly this is seen in full stack projects where there is client and server folder inside of root. And both the root and any subfolder(client,server) contains .git (git repo).

For ex if your folder looks like this->

![github.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1656934644122/0qV9unVhv.PNG align="left")

How can we  solve this problem??

-> The effective method which I found is to first create different repo for  client and server folder , push the codes for client and server code to their respective repos.

-> And then create an empty folder as well as empty repo for (client + server )code.


-> After creating the empty repo , initialise the folder with git repo  and 
then  add **submodules**( a way to tell git that all the submodules are part of this single repo only) using the following command->

```
git init

git submodule add <url> <name of module>
``` 


 ->  For ex if we consider above example then we can write


```
git submodule add <link> client
 git submodule add <link> server

``` 


-> After adding both the submodules command , you can see 2 new folders and a .gitmodule files in your root directory.
Now push this code to its empty repo which you have created earlier.


```
git add .
git commit  -m “full stack app”
git branch -M main
git remote add origin <url>
git push -u origin main

``` 

-> This will push your code to the repo and now you can see both your client and server folder inside your  [full stack app] repo, with client and server folder referring  to their original github repo.


Your final repo will look like this (just for reference)


![repo.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1656951633028/efvVC60Pp.PNG align="left")

In this the client and server are referring to their respective folders.
So in this way you can manage your code more effectively and easily.






