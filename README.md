# music-player-app
This is simple music player android app. Please contribute to the project. Please give your suggetions and contribute!!
<img width="249" alt="MainActivity" src="https://user-images.githubusercontent.com/63589114/201461721-f86c4201-88d8-4ec0-810a-4abb9fcbbe20.png">
<img width="250" alt="playSong" src="https://user-images.githubusercontent.com/63589114/201461720-13135218-af75-4663-b505-cedb72554dd9.png">

- add external storage permission in manifest
- in build.gradle of app add dependency of dexter library for runtime permission
- in dexter withcontent(this)
- with permission(externl storage permission)
- with listener(new permission listener) it will override 3 methods.
1. onpermissiongranted():if permission granted what to do
- create arraylist of mysongs and then give fetchsongs method returned songs in it
- array of items create and addd names of all songs in this array
- using for loop in items array remove mp3 from list
- using arrayadapter(context,simplelist,string of items) display it
- add onitemclicklistener on listview and using itent go to next playsong activity and send current song there as string using putextra
- songlist,currentsong,position send to next activity and startactivity
- create playsong activity
- in manifest add parentactivityname so that back button comes up
- create UI
- using bundle get intent extras
- create songs arraylist and get here using getParceblearraylist
- song name as textcontent currentsong
- and settext
- add clicklistener on all three pause play next
- take position from intent
- creare uri of song uri
- create mediaplayer and pass uri and start
- create thread and using seekbar add listener to seekbar
- mediaPlayer.seekTo(seekBar.getProgress());
                //when user click on any part of seekbar then add progress and run thread and update seekbarduration of seekbar
and mediaplayer duration in sync and setprogress of seekbar
- seekbar max set to mediaplayer duration
2. onPermissionDenied():
3. onPermissionRationaleSouldBeShown(): if user denies permission and then again opens app then agaim request permission using permissionToekn.continuePermissionRequest();

- create method fetch songs which will return public arraylist of type file
- sdcard directory is File object
- we use dynamic method dispatch
- File type external storage url we are passing to this method

- make File type array of songs which will list files of directory that we passed and go recursivly and show
- add condition for null check
- if directory is not hidden and if this is a directory then again to inside it and add songs
- if not file is mp3 and it starts with. then add to arraylist and return our arraylist
- so basically our method returns us all songs in folder
