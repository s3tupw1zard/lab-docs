## Homebrew

First install homebrew on Linux using [[01-install-homebrew]].

## Install age

Install age for creating a keypair to en- and decrypt:

```zsh
sudo apt install age
```
## Install SOPS

Install **SOPS** (**S**ecrets **OP**eration**S**)

```zsh
brew install gnupg sops
```

## Generate a Keypair using age

First create the directory .sops in your home folder or the directory you want to work with:

```zsh
mkdir .sops
```

Then generate the keypair:

```
age-keygen -o .sops/key.txt
```

The output will be like this:

```zsh
s3tupw1zard@manuel-PC:~/sops-project$ age-keygen -o .sops/key.txt
Public key: age1w06u3zky26qxnljv2jewn2vje3ul7e0nxcwzwpgvg7qsckdfk35qe364t7
s3tupw1zard@manuel-PC:~/sops-project$ 
```

## Create .sops.yml

Then create and edit a file named .sops.yaml:

```yaml
reation_rules:
  - path_regex: \.yaml$
    key_groups:
      - age:
          - "age1w06u3zky26qxnljv2jewn2vje3ul7e0nxcwzwpgvg7qsckdfk35qe364t7"
    encrypted_regex: '^(username|password|USERNAME|PASSWORD)$'

  - path_regex: \.env$
    key_groups:
      - age:
          - "age1w06u3zky26qxnljv2jewn2vje3ul7e0nxcwzwpgvg7qsckdfk35qe364t7"
    encrypted_regex: '^(username|password|USERNAME|PASSWORD)$'
```

Please remember to swap out the agesomething string with your own public key. You always can add variable names to the encrypted_regex divided by a pipe.

## Test SOPS out

Create, for example a secrets.env file:

```zsh
nano secrets.env
```

And insert ssomething like this:

```env
USER=myuser
PASSWORD='myp4ssw0rd'
```

Now after saving execute this command:

```zsh
sops -e secrets.env > secrets.enc.env
```

This is the content of the encrypted secret.enc.env file:

```env
USER=myuser
PASSWORD=ENC[AES256_GCM,data:4b7sHUdntX56oBWQ,iv:HCS8vf5kO8lzBb0j9jT+H7HAV7UlKhRXihaKcZiB+Zg=,tag:27LvWTLZ5sISbwlic6FnFA==,type:str]
sops_age__list_0__map_enc=-----BEGIN AGE ENCRYPTED FILE-----\nYWdlLWVuY3J5cHRpb24ub3JnL3YxCi0+IFgyNTUxOSBOZVFqTDBDTjN6TUg4TENL\nTmJ1WTFJSEVWNmpTbWlzUjdFeVBSR3NWS1Y4Ck9VSzYzTG1DTEFEWmRhREJ3RHcz\nSk5WcElTQnU3RFVYNFNLY05lWTBZREUKLS0tIE0yWk1Md0Uzbi9iVXFpemJ0SU1I\nNHFMZTZPTVBLUXRicDhkTXQ2eFNpV1EKQFE+PsK4cKFjrz06uS0v3AWu9s2PD2bQ\ni1XED9Fw/dxhlAIOGnUkFv+yHeDR5oubG0X3bhdbBZhP3Bd/GC2riw==\n-----END AGE ENCRYPTED FILE-----\n
sops_age__list_0__map_recipient=age1w06u3zky26qxnljv2jewn2vje3ul7e0nxcwzwpgvg7qsckdfk35qe364t7
sops_encrypted_regex=^(username|password|USERNAME|PASSWORD)$
sops_lastmodified=2024-07-08T18:54:34Z
sops_mac=ENC[AES256_GCM,data:i4cKyt1sy8yvVnoC9gjrK5G5cdndY84WDbNt85FYN/PusKYqKj2xdhrswOlENbycx19TQMNbjvNgWdLeiy+PfJX+2F18VSShp0oZmP0g7X29TGshUo4oXcdXek7Z5OG+c3G+4gBxhtGVHmg0dVynFzj4h26CFUcHIo06hOzWQX8=,iv:iPA3xIFNzWFcu0t1XHNj6ECix3mmPLG9M78rUQxDPVs=,tag:iZnGKoXJPrwOnBChiuGCow==,type:str]
sops_version=3.9.0
```

Since the variable USER is not in the regex it is not encrypted. To encrypt this we need to add USER to the regex. The line should look like this:

```yaml
encrypted_regex: '^(username|password|USERNAME|PASSWORD|USER)$'
```

After this we execute the command again:

```bash
sops -e secrets.env > secrets.enc.env
```

The content of the file now looks like this:

```env
USER=ENC[AES256_GCM,data:LJRbOpmV,iv:310C0I0N1JkKgjFNsHMBGuQwRzDfTm+5F20HQtSM//8=,tag:2W3DhMvtWebP94OlIP3JIw==,type:str]
PASSWORD=ENC[AES256_GCM,data:DxQ9/mu0E0AETeq4,iv:u+izwtZilJn+YQKMTve+ZVGRBbthLgP0F0uEvVTq8dg=,tag:XooIoKWf7Au72gdXe63Q3Q==,type:str]
sops_age__list_0__map_enc=-----BEGIN AGE ENCRYPTED FILE-----\nYWdlLWVuY3J5cHRpb24ub3JnL3YxCi0+IFgyNTUxOSBRZDR3NE5qaTBmaXppQnNF\nQ2ZsL2x3TXZwL2dMTjRtcVBFbDQ5M1R1RVE4CkVna2pFTGJTYWZtWFloSEo1endI\nVk9tTlIybGxPcDJHd053VWVGNzBYeDQKLS0tIGxYb3BjWGdaYzltTS9qRkpPOStl\nZ3h6aHVnWnNGMjZpS2owcEI3bXNjUzQKdHVuwUonv1UCYG0NuMYbdeTnWxrDDqSX\nF/LvUI3Svyz5ZDbxb98r+qjbbPtZzmrIYz33cDztCXMJGD3pzd37FA==\n-----END AGE ENCRYPTED FILE-----\n
sops_age__list_0__map_recipient=age1w06u3zky26qxnljv2jewn2vje3ul7e0nxcwzwpgvg7qsckdfk35qe364t7
sops_encrypted_regex=^(username|password|USERNAME|PASSWORD|USER)$
sops_lastmodified=2024-07-08T19:17:21Z
sops_mac=ENC[AES256_GCM,data:PoLLN4YNAC8A+y9uC0tHFleaCCMiaVjoNVsHx4P8LYGw8UxeB31uCXxdnvWrrQGFhSkxrx5m1VWsLlSxlno/kBcS0u9PtvmoQDACAEsjLlHg0GEL0KT/RdiA1YQ8mGjn5HscqRpNjQMpmspueQYOSjwighuBqjt+SIiUYDCCaHU=,iv:+H/XOGozQgsrPOUW/VcpNkKZNuS5xKb+cGYP5QCFnz4=,tag:wq51OXsLeP1/KbX844an1A==,type:str]
sops_version=3.9.0
```
