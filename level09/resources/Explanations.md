1. ls -la -> level09 (binaire) + token
2. cat token -> certains caractères "?" -> encodés
3. strings ./level09 -> on voit getenv, LD_PRELOAD, ptrace, "You should not reverse this", bon j'ai quand même tenté, mais c'était pas ça :p
4. test ./level09 token -> encodé, test ./level09 "abcd" -> "aceg" et "aaaa" -> "abcd", chaque char est décalé selon sa position : 1: +0, 2: +1, 3: +2 etc...
5. On veut décoder = inverse : char_original = char_encodé - position
6. script Python (vim /tmp/decoder.py):
data = open('/home/user/level09/token', 'rb').read()
result = ""
for i in range(len(data)):
    val = ord(data[i]) - i
    if val > 0:
        result += chr(val)
print result
7. su flag09 result -> gg