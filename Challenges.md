#  Unprintable
  Since the name suggests unprintable so we check for zero width space(ZWS)which  can be used to mark a potential line break without hyphenation in html pages so we quickly select entire text including challange title,description and check using the following link https://offdev.net/demos/zwsp-steg-js and we get the flag as hacktoberfest_ctf{zwsp_1s_1nv1s1bl3}
  
# Baby RSA  
  so "Can you prove our RSA implementation insecure?" was given as challenge description with Baby_rsa.txt with the following contents:-
  n = 0x17488abded
  e = 0x10001
  c = [77818235039, 61072516178, 69558062856, 77849934423, 19491167803, 85304110827, 31224066597, 99373816116, 86032649390]
  first we convert the hex to decimal for n and e and n will be 100001299949 wheares e will be 65537 using a very popular tool named RsaCtfTool we can now uncipher the hidden ciphertext as c using ./RsaCtfTool.py -n 100001299949 -e 65537 --uncipher "cipher" we have to do the same for each cipher/value in the ciphertext c and concatatinating the output sipts out the flag as hacktoberfest_ctf{V3ry_34sy_RSA} 
  
 # Tactile
    Here an image was given with description as 🤨Are you blind?? 🤨
Include your flag inside the flag format; i.e. hacktoberfest_ctf{FLAG}!
so since this looked like a ciphertext and i had done similar challange in nickctf so hovering over the image and a quick inspect element gives us the title as ⠧⠂⠎⠥⠲⠂⠸⠉⠗⠽⠏⠞⠕⠸⠺⠂⠞⠓⠸⠃⠗⠲⠂⠇⠇⠒ so this was using braille cipher which is for blind people using cyber chef and quickly decoding the cipher from braille we get the flag as v1su41_crypto_w1th_br41ll3 so including this inside our flag format we get hacktober_ctf{v1su41_crypto_w1th_br41ll3}

# GAIUS
    In this challange a quick google search reveals the meaning of gaius as 
    "Gaius Caesar (/ˈsiːzər/; 20 BC – 21 February AD 4) was consul in AD 1 and the grandson of Augustus, the first emperor of the Roman Empire."
    looked like a cesar cipher and quickly using https://www.dcode.fr/caesar-cipher the following we decode the flag as sh1ft_c1ph3r_n4m3d_4ft3r_jul1us_c43s4r including  the flag inside our flag format we get hacktoberfest_ctf{sh1ft_c1ph3r_n4m3d_4ft3r_jul1us_c43s4r} as our flag
    
# NOW COMES REVERSING CHALLENGES 

# TWine
   we get a binary named Twine running the binary asks us for a password and quickly running strings on it and having a closer look gives us a password as           
   y0u_g0t_17 and supplying it as the password gives us  the flag.
   
   root@leviathan:~/Documents/hacktoberfest# ./Twine 
Enter password: hello
hacktoberfest_ctf{try_ag41n}
_____now supplying the password_____ 
Enter password: y0u_g0t_17
hacktoberfest_ctf{str1ngs_2_w1n} <<= flag

# I_LOVE_SO_MANY_ARGS
  The challenge description gave a link to the video of sacar and says This song might lead you somewhere(hira thaha bhayena, flag chai hola). Just opening the binary using cutter reveals the flag which is ofc in reverse order 
 0x00001287      push    0x54       ; 'T'
 0x00001289      push    0x49       ; 'I'
 0x0000128b      push    0x5f       ; '_'
 0x0000128d      push    0x44       ; 'D'
 0x0000128f      push    0x49       ; 'I'
 0x00001291      push    0x44       ; 'D'
 0x00001293      push    0x5f       ; '_'
 0x00001295      push    0x49       ; 'I'
 0x00001297      push    0x5f       ; '_'
 0x00001299      push    0x53       ; 'S'
 0x0000129b      push    0x45       ; 'E'
 0x0000129d      push    0x59       ; 'Y'
 0x0000129f      push    0x5f       ; '_'
 0x000012a1      push    0x48       ; 'H'
 0x000012a3      mov     r9d, 0x4f  ; 'O'
 0x000012a9      mov     r8d, 0x47  ; 'G'
 0x000012af      mov     ecx, 0x41  ; 'A'
 0x000012b4      mov     edx, 0x4c  ; 'L'
 0x000012b9      mov     esi, 0x46  ; 'F'

and the flag hacktoberfest_ctf{OH_YES_I_DID_IT}.

# Supply Me Something
    So, here the challenge description said Sorry, I am programmed to only argue with 1337s.
   downloading the binary to our machine and running it gives hacktoberfest_ctf{try_4g41n} so first 
   Analysing the binary i found its checking if the supplied args is 1337 so a function call is made which pushed the local values and variables at stack so analysing the stack i saw the flag at memory address 0x0007fffffffde08(this address may differ from yours) ==> https://ibb.co/rtK6WBX
 
# Facebook Archive(OSINT)
  here the challange description said One of our challenge authors shared the post from our event page on Facebook just 12 hours before his presentation. Can you exfiltrate the flag from what he shared? so viewing facebook profiles of mahesh nikhil and binit i found binit sharing the post Make sure not to miss the session in 12 hours from now viewing its edit history we get the flag as hacktoberfest_ctf{h0w_4b0u7_sh4r3d_p0s7_3d17_h1st0ry}  ==> https://ibb.co/4W8793J
  
# Tweet tweet(OSINT)
   here the challange is created by captain nick lucipher since we get link to his twitter lin the challenge description https://twitter.com/naryal2580/ viewing the latest tweet from him i saw a link to 000webhost site and stumbled upon it for long time and decided to check the wayback machine so i loaded the website in wayback machine and saw last saved as october 7 and seeing the page and lol we get an image with THERE ARE NO FLAGS here so viewing the source of the page at bottom we see html comments with filename.mp4 looked like this was giving some direction towards flag again i stumbled upon this for couple of minutes and just entering the path as flag.mp4 i got a music video == > https://web.archive.org/web/20201007093142/https://w38-ho0k.000webhostapp.com/flag.mp4 and having a closer look at the video for 3 or 4 times i figured out a weird white text in one of the frame halfway near the ending which wasnt visible so i saved the screenshot of that frame and loaded the image in photo editor then lowered the brightness and made the image more sharper and saw flag as hacktoberfest_ctf{rickrolled_for_the_flag}
   
#  I Cee Macha Pokhari, where cow spoke(MISC)
     Here we are given a pcapng file so at first loading the file in wireshark and our analysis begins here since the challenge description mentioned 127.0.0.1 
     as highlighted text setting the filter as 127.0.0.1 we see Cow Esolang areas now joining all the sections and decoding using https://tio.run/#cow we get the      
     flag as "hacktoberfest_ctf{kassam_gai_le_bolyoo_ma_dhateko_hoina}"
     
# CTF 101(MISC)
      the challenge description says Only the people who attended the presentation on "Getting Started with CTF 101" can solve this challenge. Did you attend?
      since i had attended the session we got to see a flag at the end of binit ghimire's presentation who is also one of the challange authors as hacktoberfest_ctf{TH4NK_Y0U_F0R_4TT3ND1NG!}
    
# WEB(HARD)
    THIS BEING ONE OF MY FAVOURITE CHALLANGE I MADE A VIDEO ITSELF ON IT EXPLAINING EVERY STEP IN DETAIL AND HERE IS THE LINK TO THE VIDEO
    https://youtu.be/NK0B9aMwJIk 
