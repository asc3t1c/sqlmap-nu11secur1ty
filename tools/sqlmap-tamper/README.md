# sqlmap-tamper
SQLmap tamper scripts 


General tamper option and tamper's list
```
--tamper=tamper_name
```
- - last year
- - - Full usage:

```bash
--tamper=0eunion,apostrophemask,apostrophenullencode,appendnullbyte,base64encode,between,binary,bluecoat,chardoubleencode,charencode,charunicodeencode,charunicodeescape,commalesslimit,commalessmid,commentbeforeparentheses,concat2concatws,decentities,dunion,equaltolike,equaltorlike,escapequotes,greatest,halfversionedmorekeywords,hex2char,hexentities,htmlencode,if2case,ifnull2casewhenisnull,ifnull2ifisnull,informationschemacomment,least,lowercase,luanginx,misunion,modsecurityversioned,modsecurityzeroversioned,multiplespaces,ord2ascii,overlongutf8,overlongutf8more,percentage,plus2concat,plus2fnconcat,randomcase,randomcomments,schemasplit,scientific,sleep2getlock,sp_password,space2comment,space2dash,space2hash,space2morecomment,space2morehash,space2mssqlblank,space2mssqlhash,space2mysqlblank,space2mysqldash,space2plus,space2randomblank,substring2leftright,symboliclogical,unionalltounion,unmagicquotes,uppercase,varnish,versionedkeywords,versionedmorekeywords,xforwardedfor
```

| Tamper | Description |
| --- | --- |
|apostrophemask.py | Replaces apostrophe character with its UTF-8 full width counterpart |
|apostrophenullencode.py | Replaces apostrophe character with its illegal double unicode counterpart|
|appendnullbyte.py | Appends encoded NULL byte character at the end of payload |
|base64encode.py | Base64 all characters in a given payload  |
|between.py | Replaces greater than operator ('>') with 'NOT BETWEEN 0 AND #' |
|bluecoat.py | Replaces space character after SQL statement with a valid random blank character.Afterwards replace character = with LIKE operator  |
|chardoubleencode.py | Double url-encodes all characters in a given payload (not processing already encoded) |
|commalesslimit.py | Replaces instances like 'LIMIT M, N' with 'LIMIT N OFFSET M'|
|commalessmid.py | Replaces instances like 'MID(A, B, C)' with 'MID(A FROM B FOR C)'|
|concat2concatws.py | Replaces instances like 'CONCAT(A, B)' with 'CONCAT_WS(MID(CHAR(0), 0, 0), A, B)'|
|charencode.py | Url-encodes all characters in a given payload (not processing already encoded)  |
|charunicodeencode.py | Unicode-url-encodes non-encoded characters in a given payload (not processing already encoded)  |
|equaltolike.py | Replaces all occurances of operator equal ('=') with operator 'LIKE'  |
|escapequotes.py | Slash escape quotes (' and ") |
|greatest.py | Replaces greater than operator ('>') with 'GREATEST' counterpart |
|halfversionedmorekeywords.py | Adds versioned MySQL comment before each keyword  |
|ifnull2ifisnull.py | Replaces instances like 'IFNULL(A, B)' with 'IF(ISNULL(A), B, A)'|
|modsecurityversioned.py | Embraces complete query with versioned comment |
|modsecurityzeroversioned.py | Embraces complete query with zero-versioned comment |
|multiplespaces.py | Adds multiple spaces around SQL keywords |
|nonrecursivereplacement.py | Replaces predefined SQL keywords with representations suitable for replacement (e.g. .replace("SELECT", "")) filters|
|percentage.py | Adds a percentage sign ('%') infront of each character  |
|overlongutf8.py | Converts all characters in a given payload (not processing already encoded) |
|randomcase.py | Replaces each keyword character with random case value |
|randomcomments.py | Add random comments to SQL keywords|
|securesphere.py | Appends special crafted string|
|sp_password.py |  Appends 'sp_password' to the end of the payload for automatic obfuscation from DBMS logs |
|space2comment.py | Replaces space character (' ') with comments |
|space2dash.py | Replaces space character (' ') with a dash comment ('--') followed by a random string and a new line ('\n') |
|space2hash.py | Replaces space character (' ') with a pound character ('#') followed by a random string and a new line ('\n') |
|space2morehash.py | Replaces space character (' ') with a pound character ('#') followed by a random string and a new line ('\n') |
|space2mssqlblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
|space2mssqlhash.py | Replaces space character (' ') with a pound character ('#') followed by a new line ('\n') |
|space2mysqlblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
|space2mysqldash.py | Replaces space character (' ') with a dash comment ('--') followed by a new line ('\n') |
|space2plus.py |  Replaces space character (' ') with plus ('+')  |
|space2randomblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
|symboliclogical.py | Replaces AND and OR logical operators with their symbolic counterparts (&& and ||) |
|unionalltounion.py | Replaces UNION ALL SELECT with UNION SELECT |
|unmagicquotes.py | Replaces quote character (') with a multi-byte combo %bf%27 together with generic comment at the end (to make it work) |
|uppercase.py | Replaces each keyword character with upper case value 'INSERT'|
|varnish.py | Append a HTTP header 'X-originating-IP' |
|versionedkeywords.py | Encloses each non-function keyword with versioned MySQL comment |
|versionedmorekeywords.py | Encloses each keyword with versioned MySQL comment |
|xforwardedfor.py | Append a fake HTTP header 'X-Forwarded-For'|
