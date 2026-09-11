# Homelab Setup — Night 2

## Where I'm At
I started the COMPTIA textbook that I have and studied for about an hour before work and 
right after my Kali Virtual Machine is done updating I will try to get in another 30min to 
an Hour before bed, overall I am pretty happy with where I'm at, but I also need to learn 
GitHub a little bit more, I think the most important thing that I am taking away from 
tonight is that AI is not really the way to go with starting this HomeLab so rather then 
just opening up Claude and seeing hat it will have me do, I am going to research home labs 
and how to view Live DNS traffic with PiHole and will troubleshoot myself. 

## What I set out to do
Get Pi-hole showing live DNS traffic, run my first network scan from Kali, 
and fix ongoing VirtualBox Guest Additions issues (screen resize, clipboard, 
display flickering).

## What happened
- Did absolutely nothing as far as fixing the issue of not being able to see live DNS
  traffic, instead got hung up on the screen not resizing, and not being able to copy text
  from the browser over to the Virtual Machine
- Learned that in terminal every little detail matters, obviously spelling, but
  capitalization matters, as well as making sure you have the exact file name down to each
  character, or you will receive an error message. In the future I see the importance of
  double checking actual file names and commands because even the information online can
  be dated which will cause a bigger issue then needed. Using "-ls" I can list the files
  in any given folder, and double check if I am calling or working with the right name. 

## How I fixed it
- Rebuilt Kali clean: deleted the conflicted VM entirely, re-extracted the 
  original `.7z` (no re-download needed), and re-imported via `Machine > 
  Open`. Resize worked immediately, confirming Kali's pre-built image ships 
  with working Guest Additions already — the manual install was the actual 
  cause of the problem, not a missing feature.
- Changed the default `kali` password using `passwd`.

## What I learned
- Installing something manually on top of a feature that's already 
  pre-installed can cause a conflict that looks like a completely different, 
  unrelated bug (display glitching led me toward graphics settings, when the 
  real cause was a duplicate driver install).
- When troubleshooting stalls after several fix attempts, rebuilding clean 
  from an untouched source can be faster than continuing to patch a state 
  that's already been modified multiple conflicting ways.
- Artificial Intelligence is a great learning tool to use during this journey, but that
  is all it should be used as. AI has created more problems for me then it has fixed and
  luckily I am not a complete idiot and made up for my lack of knowledge and context skills
  to figure out that recreating the kali Virtual Machine would be easier then continuing to
  diagnose a problem that was created by AI not understanding what was actually happening.

## Still open
- Haven't yet fixed the issue of why I am unable to see live DNS traffic, but it seems
  like a good starting point for tomorrow.
- I also need to fix the power issue that I created on my "PiStack" by using a charger
  that was too powerful, and need to remember that these are not iPhones and popular
  devices, these are real learning tools and I need to pay attention to voltage and things
  that can actually damage the technology 
- Haven't yet run the planned `nmap -sn` scan of the home network from Kali








