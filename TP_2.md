# Sujet 2 : Débugger et désassembler des programmes compilés.

## Exercices.

### Hello Word.
```
#include <stdio.h>

int main(void)
{
    printf("Hello World!\n");
    return 0;
}
````
(Langage utilisé dans Ghidra, le tout premier **"default"**)

La chaîne de caractère **"Hello World"** est stocker dans la partie **"ACLR"** et est présenter de cette façon :
```
                             ACLR
            001b 61              ??         61h    a
            001c 69              ??         69h    i
            001d 6e              ??         6Eh    n
            001e 28              ??         28h    (
            001f 76              ??         76h    v
            0020 6f              ??         6Fh    o
            0021 69              ??         69h    i
            0022 64              ??         64h    d
            0023 29              ??         29h    )
            0024 0d              ??         0Dh
            0025 0a              ??         0Ah
            0026 7b              ??         7Bh    {
            0027 0d              ??         0Dh
            0028 0a              ??         0Ah
            0029 20              ??         20h     
            002a 20              ??         20h     
            002b 20              ??         20h     
            002c 20              ??         20h     
            002d 70              ??         70h    p
            002e 72              ??         72h    r
            002f 69              ??         69h    i
            0030 6e              ??         6Eh    n
            0031 74              ??         74h    t
            0032 66              ??         66h    f
            0033 28              ??         28h    (
            0034 22              ??         22h    "
            0035 48              ??         48h    H
            0036 65              ??         65h    e
            0037 6c              ??         6Ch    l
            0038 6c              ??         6Ch    l
            0039 6f              ??         6Fh    o
            003a 20              ??         20h     
            003b 57              ??         57h    W
            003c 6f              ??         6Fh    o
            003d 72              ??         72h    r
            003e 6c              ??         6Ch    l
            003f 64              ??         64h    d
            0040 21              ??         21h    !
            0041 5c              ??         5Ch    \
            0042 6e              ??         6Eh    n
            0043 22              ??         22h    "
            0044 29              ??         29h    )
            0045 3b              ??         3Bh    ;
```

### Winrar crack.

Pour effectuerle crack de Winrar nous avons utilisé **x64dbg** qui est un débugger pour windows qui permet de voir le code assembleur des programmes.

* 1 : Ouvrir **x64dbg**.
* 2 : Aller dans **Fichier** et ouvrir le **".exe"** de Winrar.
* 3 : Ensuite cliquez sur **Symboles** et double-clic sur **winrar.exe**.
* 4 : Clique droit sur la première ligne (lea rcx,...) puis cliquez sur **"Recherche pour"** , **"Module courant"** , **"Références à des chaînes de caractères"**.
* 5 : Dans la barre de recherche tapez **"rarkey"** et double cliquez sur la deuxième ligne.
* 6 : Ensuite remontez un petit peu avec la flèche du haut, jusqu'à tomber sur **"jmp winrar.7FF7A99B0C88"**.
* 7 : Faire clique droit sur cette ligne et cliquez sur **"Binaire"**, **""Remplir avec des NOPs""**, et cliquez sur **"ok"** en faisant aucune modif.
* 8 : Deux lignes **"nop"** vont être crée et mis en surbrillance, cliquez sur le pansement pour faire un patch.
* 9 : Cliquez sur **"fichier de patch"**, enregistrer sur le bureau en mettant par exemple **"Wincrack.exe"**, ne pas oubliez le **".exe"**, puis enregistrer
* 10 : Ouvrez votre nouveau **".exe"**, puis **"help"**, **"About winrar"** et enfin vous verrez une ligne disant **"Register to"** et voilà.