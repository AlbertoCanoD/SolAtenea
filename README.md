# SolAtenea

Soluciones y razonamientos de los retos de Atenea del CCN-CERT

---

## Básica

### Hash

Se calcula el hash md5 de la contraseña "LearnTheHashFunction".

`echo -n "LearnTheHashFunction" | md5sum`

### Hash 2

Se calcula el hash sha256 de la contraseña "ThisIsAMoreSecureHashFunction".

`echo -n "ThisIsAMoreSecureHashFunction" | sha256sum`

Y una vez tengamos la cadena calculada en sha256 la calculamos con md5.

`echo -n "d191ce0a9d8061acb609be613d0a6dccd13d93946fa3e8aa3c0c40a2102502ff" | md5sum`

### Hash 3

Para hacer reverse del md5, se entra a alguna web, por ejemplo [https://crackstation.net/](https://crackstation.net/), convertimos la cadena a mayúsculas y calculamos el hash md5 con md5sum

### Base64

Se decodifica el texto en base64 utilizando el paquete con el mismo nombre.

`echo -n "UmVjdWVyZGEgcXVlIGN1YW5kbyBjb2RpZmljYXMgYWxnbyBlbiBiYXNlNjQgTk8gbG8gZXN0w6Fz
IGNpZnJhbmRvLCBzaW5vIHF1ZSBzaW1wbGVtZW50ZSBsbyBlc3TDoXMgY29kaWZpY2FuZG8uDQoN
CkxhIGNvbnRyYXNlw7FhIHBhcmEgc3VwZXJhciBlc3RlIHJldG8gZXM6IHJlY3VlcmRhcXVlYmFz
ZTY0Tk9lc2NpZnJhcg0KCg==" | base64 -d`

### ASCII

Para traducir de los valores ASCII a los caracteres se puede utilizar un mini-script que haga la conversión.

`echo -n "080 097 115 115 119 111 114 100 032 112 097 114 097 032 115 117 112 101 114 097 114 032 101 108 032 114 101 116 111 058 032 084 104 101 065 083 067 073 073 084 097 098 108 101 033" | awk '{ for(i=1;i<=NF;i++) printf("%c",$i); print "";  }'`

### Hex

Para convertir de hexadecimal a caracteres podemos usar el paquete xxd.

`echo -n "50617373776f72643a2044346d7054686548337821" | xxd -r -p`