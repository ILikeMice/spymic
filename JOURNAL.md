# FYI, the time in brackets shows how time much i (roughly) spent on that session

## 06.08.26
### Initial research (~3h)

So, new project yaay, for this project i wanna make some sort of device i could stick onto walls (walls in question being doors/windows too maybe?) and listen to whatevers going on on the other side <br>
Disclaimer:: im making this thing for https://ispy.hackclub.com fyi, incase ts looks weirder than my other projects :p <br>
Overall this was inspired by some laser mic videos i saw online a couple years ago and me trying to listen to some oral test in a classroom before me through my phone, also a couple years ago!! (i would never now though)

I never really worked with mics and such, and defo not with laser mics or anything, so i was completely clueless as where to even start... <br>
My first thought was to replicate the same thing the people have done in the laser mic videos on youtube, mainly by shining a laser onto a window and it reflecting onto a solar cell, whereas the vibrations of the deflected laser would be picked up due to the laser not being completely on the solar cell and therefore the output would change in intensity when the surface vibrated. <br>
Some setups i looked into looked like this:
![alt text](images/image-1.png)
![alt text](images/image-2.png)

Whereas i liked the first approach more tbh, but the 2nd one is cool too. The only problem(s) with this are though that <br>
1. if i attached the laser and the probe mirror as per the first approach (theres one control and one probe mirror, the probe mirror is on the vibrating surface) to the same surface, from the lasers POV there wouldnt be any sound or vibrations, so it wouldnt work at all.
2. the 2nd approach wouldnt really work either due to point 1. and the fact that im trying to attach this to a door, which MIGHT not be as reflective as a mirror/window, so were not getting any response on that either...

After the cool laser idea has been shattered, i decided to look into some other types of mics and found out about contact mics! They seem to be pretty cheap, and, after checking out some questionable vids about guys building them, i liked their quality enough and decided to use them!
![alt text](images/image-3.png)
shoutout this cool guy from 14 years ago on [youtube](https://www.youtube.com/watch?v=aOJuCYgmPPE) for demonstrating all that

Also started doing some research on components to use in the project, and got some example schematics to maybe use later on! Turns out piezo discs are real cheap, so i can make lots of these is the pcb and components are also cheap!! (for education purposes only)

![alt text](images/image.png)

Thats all for now, ive got some more features in mind that id love to add, but its about midnight here and id probably work on this tmrw!

## 08.08.26
### More research (~3.5h)

As the title suggests, i did some more research on this stuff. Mainly messed around in falstad though with the circuit but there was a fair share of researching done!!
<br>
So, at first i tried copying the circuit above into falstad, and after searching it up, i could replace the mic with an AC source in series with a capacitor with the capacitance of the mic.

![alt text](images/image-5.png)
![alt text](images/image-6.png)

<br>

For some reason, even after messing around with it for a while, that didnt work at all, so after looking some more stuff up and trying different configurations i just gave up, until i discovered opamps exist!! That seemed to be way easier and i had a circuit working almost directly!

![alt text](images/image-7.png)

<br> 
that was until i tried using a real opamp, which for some reason fucked everything up and just flatlined..

![alt text](images/image-8.png)
<br>

the fix for the flatline was me being dumb and having the polarity of the opamp power reversed, and turns out i needed a pulldown resistor for the wave maximum to not go down slowly after that, for some reason i cant be bothered to understand, im just glad this shit finally works

![alt text](images/image-9.png)

Also started doing the schematic in kicad, but that took waayy longer than i thought, since i cant just feed 9v into the average opamp IC, so i had to look into buck converters after first finding an IC thats good enough and understanding what all the specs are

![alt text](images/image-10.png)

didnt help much either that the datasheets for buck converters are ALL in chineese

![alt text](images/image-11.png)