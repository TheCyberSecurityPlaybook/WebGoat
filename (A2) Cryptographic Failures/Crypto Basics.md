
### 1. Base64 Encoding

![](images/image1.png)


dXNlcm5hbWUxOmFkbWlu
 
username1:admin

![[Pasted image 20260602155728.png]]

### 2. Other Encoding

![[Pasted image 20260602200155.png]]



 Способы декодирования паролей

- **Онлайн-сервисы.** можно использовать сайт 
    
    poweredbywebsphere.com/decoder.html
        В таких инструментах обычно требуется ввести зашифрованный пароль без префикса  

{xor}Oz4rPj0+LDovPiwsKDAtOw==

Расшифрованная строка:  databasepassword

![[Pasted image 20260602215429.png]]

### 3. Plain Hashing

![[Pasted image 20260603102137.png]]

Алгоритм хеширования: MD5
21232f297a57a5a743894a0e4a801fc3:admin

Алгоритм хеширования: SHA256X1PLAIN
8d969eef6ecad3c29a3a629280e686cf0c3f5d5a86aff3ca12020c923adc6c92:123456

![[Pasted image 20260603102201.png]]

### 4. Signature 

![[Pasted image 20260603105955.png]]

-----BEGIN PRIVATE KEY-----
MIIEvAIBADANBgkqhkiG9w0BAQEFAASCBKYwggSiAgEAAoIBAQC1vRqQZ4SGAdhzOpCQ2JQoLVmZ6NOWCrSih1WBoyD46srGlLIlj3trkQwj+C39GRk8x+WYHHfmwBzw4BJuXiMAmlzGKRYvK696O4aDZZBawwR8GCIdbcaCTfCLprHXBkfFMx0tKW5vnqIG0sfsQWtosXU0+tF42hKRk2WT/CenhzLa231t5C6Qc1OmH/0uJ+Ozos88HUwEnNjaEGe+zejzM2T1yUbfCrTfJfurW+rhvmVa1LIffV2HtFqIfwj1CMVylbHm9xbi7uKVDUQxuWqMboQhmSs5kMQPNGlid03SbS8NEjbbiPeiHZ3wG7IG48Muo7WcQlapdeJl4HqNjhIxAgIBAQKCAQANUW1cQ1o69iyVOj9jRKo8DfLPWJ2d693BiMFeVdUX4riHvtw+2d8KtHdCuAoCxpIehNqJfJuL7d7sy7BVc85vcT8+qrBxXFpjxPFz4Wyx+112/3G7bs9LSsZr2j6BetDMNbeYj1JNk0L91/8LgKTCHEctjZDYNn8z1yt4QCIeCkgL3f1n2AjLNa3phrn7QVDkj+n29SbAes4oPL/9ewHpTmn48mAYM4LgIP5yOjNfmlTzGuFGslCa6YoQ38MP7Gnpn9NasWpdIxXdInYvXXTxrauzGLmzPeQTNib+hmhWGcI1oOScylMvDY8AFitq0ceISAoF2iOFI6n7X9nwLWIfAoGBAO+zp0CgoBlYYd1WxVQFD6INyutCUCDgGALoRGKewKauZ1/JGZHg58pWkU9Cb7yPH3MSueFEwBsXSkWWrdXZJ4fPWGbpurb/h0gQ9m1bpJ52CMaHNue8ybR8oF7WCCi5AuiuwFc4sZRPlJJaP0i7vpRCm41RwHKWHmNUSB+Zr6VzAoGBAMIYhXkf9nIssY38XgV795Kh7JrdaAFp3di4VB9QBqBB1p6Bm3g70Lx/dY2Bv9l9/LgVhX9woessNqI9ZN9pGdNBUlzu//80804uBawQTZcQM6+B9/CtJGhjo3wYoebhoo9MIgGLPgiVjA9QtvJOuVyGWeN7yD7NNewYFCdxKqDLAoGBANwdgK7lLmj0hbJZpEUveu52QNAREM2BFQ2gfoxd+54KvI+9peyOxuegLcdJ9QzHKdRBAllSDwnviO83sJCTnNRexrgnUM/jrQlmPO/gmybt4jTP1sbbLsOfRJLadRB6FJnnMh5J+br+XphS33eVfjJ67HnNj9nIm2gpiPQtgGwZAoGAUlIetdy/L22Z/3T/CUx77YFwTaKipfQfVfCLRg8Dzm2axrZ4uXf/4GHjKhYohxORCVfSBT23OefrV7xni5Qr0x+wYTCSbTxPSQCX0nCAiMkc5NWBEGlPMUErcGYW2HWcmmkBeS8aT1hUTjcmvm0X1JCjojl6x/VqivtFT3uzcwMCgYBnaHwP0l4jOuAPNe8YBImVA4CChPi7lTK6VetR0XPkEEu/3TyOcZ7trxE5O6fF4hr66yAkAbwh83WEsvC5isUgVfm8/CFjkO+TIf8VAbYnfPWuw1lWjHrfIttQk/jj45OJUiteWFpV3+lontQQlwvm7RuuZcl2xwdPuVPtlATkvg==
-----END PRIVATE KEY-----


Имеется закрытый RSA-ключ. Определите модуль RSA-ключа в виде шестнадцатеричной строки и вычислите подпись для этой шестнадцатеричной строки, используя ключ

Показать модуль для файла ключа:  
_openssl rsa -noout -modulus -in privkey.pem


Извлекает открытый ключ из приватного RSA‑ключа:
```
openssl rsa -in test.key -pubout -out test.pub
```
![[Pasted image 20260603121517.png]]

Выводит содержимое файла `test.pub` на экран
```
cat test.pub 
```
![[Pasted image 20260603122534.png]]

-----BEGIN PUBLIC KEY-----
MIIBITANBgkqhkiG9w0BAQEFAAOCAQ4AMIIBCQKCAQEAtb0akGeEhgHYczqQkNiU
KC1ZmejTlgq0oodVgaMg+OrKxpSyJY97a5EMI/gt/RkZPMflmBx35sAc8OASbl4j
AJpcxikWLyuvejuGg2WQWsMEfBgiHW3Ggk3wi6ax1wZHxTMdLSlub56iBtLH7EFr
aLF1NPrReNoSkZNlk/wnp4cy2tt9beQukHNTph/9Lifjs6LPPB1MBJzY2hBnvs3o
8zNk9clG3wq03yX7q1vq4b5lWtSyH31dh7RaiH8I9QjFcpWx5vcW4u7ilQ1EMblq
jG6EIZkrOZDEDzRpYndN0m0vDRI224j3oh2d8BuyBuPDLqO1nEJWqXXiZeB6jY4S
MQICAQE=
-----END PUBLIC KEY-----

 Получает модуль (modulus) открытого RSA‑ключа
```
-> % openssl rsa -in test.pub -pubin -modulus -noout
```
![[Pasted image 20260603122609.png]]

Modulus=B5BD1A9067848601D8733A9090D894282D5999E8D3960AB4A2875581A320F8EACAC694B2258F7B6B910C23F82DFD19193CC7E5981C77E6C01CF0E0126E5E23009A5CC629162F2BAF7A3B868365905AC3047C18221D6DC6824DF08BA6B1D70647C5331D2D296E6F9EA206D2C7EC416B68B17534FAD178DA1291936593FC27A78732DADB7D6DE42E907353A61FFD2E27E3B3A2CF3C1D4C049CD8DA1067BECDE8F33364F5C946DF0AB4DF25FBAB5BEAE1BE655AD4B21F7D5D87B45A887F08F508C57295B1E6F716E2EEE2950D4431B96A8C6E8421992B3990C40F346962774DD26D2F0D1236DB88F7A21D9DF01BB206E3C32EA3B59C4256A975E265E07A8D8E1231

Подписывает данные (в данном случае — шестнадцатеричное представление модуля) с помощью приватного ключа
```
echo -n "B5BD1A9067848601D8733A9090D894282D5999E8D3960AB4A2875581A320F8EACAC694B2258F7B6B910C23F82DFD19193CC7E5981C77E6C01CF0E0126E5E23009A5CC629162F2BAF7A3B868365905AC3047C18221D6DC6824DF08BA6B1D70647C5331D2D296E6F9EA206D2C7EC416B68B17534FAD178DA1291936593FC27A78732DADB7D6DE42E907353A61FFD2E27E3B3A2CF3C1D4C049CD8DA1067BECDE8F33364F5C946DF0AB4DF25FBAB5BEAE1BE655AD4B21F7D5D87B45A887F08F508C57295B1E6F716E2EEE2950D4431B96A8C6E8421992B3990C40F346962774DD26D2F0D1236DB88F7A21D9DF01BB206E3C32EA3B59C4256A975E265E07A8D8E1231" | openssl dgst -sha256 -sign test.key
```

 Результат сохраняется в файл.
```
echo -n "B5BD1A9067848601D8733A9090D894282D5999E8D3960AB4A2875581A320F8EACAC694B2258F7B6B910C23F82DFD19193CC7E5981C77E6C01CF0E0126E5E23009A5CC629162F2BAF7A3B868365905AC3047C18221D6DC6824DF08BA6B1D70647C5331D2D296E6F9EA206D2C7EC416B68B17534FAD178DA1291936593FC27A78732DADB7D6DE42E907353A61FFD2E27E3B3A2CF3C1D4C049CD8DA1067BECDE8F33364F5C946DF0AB4DF25FBAB5BEAE1BE655AD4B21F7D5D87B45A887F08F508C57295B1E6F716E2EEE2950D4431B96A8C6E8421992B3990C40F346962774DD26D2F0D1236DB88F7A21D9DF01BB206E3C32EA3B59C4256A975E265E07A8D8E1231" | openssl dgst -sha256 -sign test.key -out data.sign
```

Вывести содержимое файла `data.sign` на экран
```
cat data.sign 
```
![[Pasted image 20260603122653.png]]

   
Кодирует бинарный файл с подписью в формат Base64
```
 openssl base64 -in data.sign -out data64.sign 
```

Выводит содержимое файла `data64.sign` на экран
 ```
 cat data64.sign
 ``` 
![[Pasted image 20260603122725.png]]


FGwPChccvuukK3VrIKXP4Hk3Dt2CRK2hFO8YcdFbLbstDc7OuxwRUcvx4s7AQe2h
EVTyx2aHyNjfbZ4N/Vy9lqUlEmimNMGoXEbP8UtIVeCAuGpoe1U4IeZJ1yCf60ij
XO2u3WSgvL/PFclgd8vy/BFaEcIoEoeOEncbhHcyrAJ9alsZpXZJdeEzfu9LN5jf
SmSeeZuSbN3mBg/uOPiuyfGvORJEZRGBLbSEsQ9aikM6XOpxo2L2vzx2SS5/+FdA
utc5Db3fC3PeY82hgLsli11JayEvMCbide4j66z5TVAcvUj3Rl45dugRiBIJXLiK
i1Oe/Nbi9gWdJ5q2lHrVWg==

Ссылки на источник: 
https://lindevs.com/sign-and-verify-file-signature-with-public-and-private-key-using-openssl
https://lindevs.com/extract-public-key-from-private-key-using-openssl

![[Pasted image 20260603120741.png]]

Java cacerts
![[Pasted image 20260604112229.png]]

```
docker run -d webgoat/assignments:findthesecret
echo "U2FsdGVkX199jgh5oANElFdtCxIEvdEvciLi+v+5loE+VCuy6Ii0b+5byb5DXp32RPmT02Ek1pf55ctQN+DHbwCPiVRfFQamDmbHBUpD7as=" | openssl enc -aes-256-cbc -d -a -kfile ....
```

После запуска контейнера Docker войдите в него, используя команду
`docker exec -ti _dockerid_ /bin/bash`

```
sudo docker exec -ti 2d3f0d3d59d4051b9caf7bcaf5b87e774b437fdd88f56d37d62475a4113abfb9 /bin/bash
```

![[Pasted image 20260604113043.png]]

$ docker cp 2d3f0d3d59d4:/etc/passwd ~/passwd1

$ docker cp 2d3f0d3d59d4:/etc/shadow ~/shadow1

$ openssl passwd -1 salt evil evil

$1$Pl8RVShL$JobKSgzYd/A7liu0EOUfn.
$1$W8yitsN3$RdDL/sGxwRQiZlQwB9Shn.
$1$PS0wQNT7$1cqSspv5KkHwABP67LElS.

docker cp passwd 2d3f0d3d59d4:/etc

$1$Pl8RVShL$JobKSgzYd/A7liu0EOUfn.



Delete docker container:

```
docker stop $(docker ps -qa)

docker container prune --force
```


![[Pasted image 20260605103548.png]]

![[Pasted image 20260605103618.png]]


```
cat default_secret 
```

ThisIsMySecretPassw0rdF0rY0u

```
echo "U2FsdGVkX199jgh5oANElFdtCxIEvdEvciLi+v+5loE+VCuy6Ii0b+5byb5DXp32RPmT02Ek1pf55ctQN+DHbwCPiVRfFQamDmbHBUpD7as=" | openssl enc -aes-256-cbc -d -a -kfile default_secret
```

![[Pasted image 20260605104013.png]]

> `webgoat@c06f28f993b4:/$ su evil`
> Password: 
> `root@c06f28f993b4:/# cd`
> `root@c06f28f993b4:~# ls`
> default_secret
> `root@c06f28f993b4:~# cat default_secret ``
> ThisIsMySecretPassw0rdF0rY0u
> `root@c06f28f993b4:~# echo "U2FsdGVkX199jgh5oANElFdtCxIEvdEvciLi+v+5loE+VCuy6Ii0b+5byb5DXp32RPmT02Ek1pf55ctQN+DHbwCPiVRfFQamDmbHBUpD7as=" | openssl enc -aes-256-cbc -d -a -kfile default_secret`
> Leaving passwords in docker images is not so secureroot@c06f28f993b4:~# 


![[Pasted image 20260605104219.png]]




