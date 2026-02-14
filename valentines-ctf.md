# Valentine’s Cyber CTF for My Wife 💘

A light, playful CTF you can run at home with a laptop and your phone.

## How to Run This CTF

- **Format:** 8 mini-challenges
- **Difficulty:** Beginner to intermediate
- **Theme:** Love notes, memories, and puzzles
- **Flag format:** `VAL{...}`
- **Scoring suggestion:** 100 points each (bonus 50 for no hints)

---

## Challenge 1 — "Our First Date" (Caesar Cipher)

**Category:** Crypto  
**Difficulty:** Easy  
**Points:** 100

### Player prompt
> I wrote you a note, but I shifted every letter by 3.  
> `YDO{L_oryh_rx}`

### Goal
Recover the original flag.

### Expected flag
`VAL{I_love_you}`

### Hint (optional)
Try shifting letters backward.

### Setup notes
Just hand over the ciphertext in a note/text message.

---

## Challenge 2 — "Secret in the Roses" (Acrostic)

**Category:** OSINT/Puzzle  
**Difficulty:** Easy  
**Points:** 100

### Player prompt
> Read this poem carefully:
>
> **V**iolets by moonlight softly gleam  
> **A**ll my favorite nights include you  
> **L**aughter turns each day into a dream  
> **E**very little memory feels new  
> **N**othing in this world compares at all  
> **T**ime with you is all I ever need  
> **I** still fall harder every single call  
> **N**ever doubt my heart in word or deed  
> **E**ach first letter matters.

### Goal
Extract the hidden word and submit as a flag.

### Expected flag
`VAL{VALENTINE}`

### Hint (optional)
Take the first letter of each line.

### Setup notes
Can be printed as a card insert.

---

## Challenge 3 — "Pixel Love" (Steganography)

**Category:** Forensics  
**Difficulty:** Medium  
**Points:** 100

### Player prompt
> I hid something in an image called `roses.png`.

### Goal
Find hidden text in image metadata or LSB stego.

### Expected flag
`VAL{you_found_the_hidden_kiss}`

### Hint (optional)
Try `strings roses.png`, then metadata tools (`exiftool`) if needed.

### Setup notes
- Create any flower image.
- Embed comment metadata:
  - Example: `exiftool -Comment="VAL{you_found_the_hidden_kiss}" roses.png`

---

## Challenge 4 — "Playlist Password" (Base64 + ZIP)

**Category:** Misc/Crypto  
**Difficulty:** Medium  
**Points:** 100

### Player prompt
> I left you this string:
> `VkFMe2hlYXJ0c19hbmRfa2lzc2VzfQ==`
>
> and this file: `gift.zip`

### Goal
Decode the string and use it as ZIP password.

### Expected decoded password
`VAL{hearts_and_kisses}`

### ZIP contents
`next.txt` containing: `Flag: VAL{music_of_my_heart}`

### Setup notes
1. Put `next.txt` in a ZIP.
2. Password-protect ZIP with `VAL{hearts_and_kisses}`.

---

## Challenge 5 — "Dinner Reservation" (SQLi - gentle)

**Category:** Web  
**Difficulty:** Medium  
**Points:** 100

### Player prompt
> A tiny local web page asks for a reservation code.  
> “Only valid couples can continue.”

### Goal
Bypass login using basic SQL injection.

### Vulnerable query (intentionally insecure)
```sql
SELECT * FROM couples WHERE code = '$input';
```

### Example payload
`' OR '1'='1` 

### Expected flag after bypass
`VAL{you_hacked_my_heart}`

### Setup notes
Host a toy local page only (no real internet exposure).

---

## Challenge 6 — "The Missing Message" (PCAP)

**Category:** Network  
**Difficulty:** Medium  
**Points:** 100

### Player prompt
> I captured some network traffic in `love.pcap`.  
> One packet contains the flag in plain HTTP.

### Goal
Open with Wireshark and follow HTTP stream.

### Expected flag
`VAL{sniffed_with_love}`

### Setup notes
Generate a tiny HTTP request containing `GET /?flag=VAL{sniffed_with_love}`.

---

## Challenge 7 — "Hash of Affection" (Cracking)

**Category:** Crypto  
**Difficulty:** Medium  
**Points:** 100

### Player prompt
> Can you recover this password hash?
> `5f4dcc3b5aa765d61d8327deb882cf99`

### Goal
Identify hash type and crack it.

### Expected password
`password`

### Submit flag
`VAL{password}`

### Hint (optional)
Try common hash databases or wordlists.

---

## Challenge 8 — "Final Treasure" (Multi-step)

**Category:** Mixed  
**Difficulty:** Medium+  
**Points:** 150

### Player prompt
> Combine all previous flags’ keywords (inside braces), ordered by challenge number, separated by `-`, then SHA1 it.
>
> Format to hash:
> `I_love_you-VALENTINE-you_found_the_hidden_kiss-music_of_my_heart-you_hacked_my_heart-sniffed_with_love-password`

### Goal
Compute SHA1 and submit final flag.

### Expected final flag
`VAL{84093565b00cb9ae335dbfb192b59cca64549d94}`

### Setup notes
Use this as the final “unlock” before giving real-world prize.

---

## Reward Ideas 🎁

- Printed “certificate of pwnage”
- Hidden chocolate stash
- Surprise date clue at final flag

## Optional Physical Finale
When she submits final flag, hand over a sealed envelope saying:

> “Root access granted to my heart forever. ❤️”

