# type_proot_install

# EXPLICAÇÃO SIMPLES DE COMO EU EXECUTO ISSO NORMALMENTE NO MEU CELULAR:

## INSTALE O 'TERMUX' APK E O 'TERMUX:X11' APK DO 'F-DROID'
https://f-droid.org/pt_BR/packages/com.termux/
https://github.com/termux/termux-x11/releases

> [!NOTE]
> **O 'Termux:X11' só está disponível para 'Android 8.0' ou superior.**
> **Caso esteja em um Android 7.1 ou inferior, recomendo usar VNC no lugar. Mas a experiência não será boa devido a possível latência.**

## OPCIONALMENTE INSTALE O TERMUX:API
https://f-droid.org/pt_BR/packages/com.termux.api/

## ABRA O TERMUX, EXECUTE E PERMITA ACESSO AO ARMAZENAMENTO EXTERNO AO TERMUX:
```bash
termux-setup-storage
```

## TENHA NA HOME O ARQUIVO.ZIP DAS SEGUINTES FORMAS:

## 1. USANDO WGET

```bash
pkg update && pkg install -y wget
cd ~
wget -O type_proot_install.zip https://github.com/diogoeae1/type_proot_install/releases/download/v1.0/type_proot_install.zip
```

## BAIXE MANUALMENTE E NAVEGUE ATÉ A PASTA ALVO DO SEU CELULAR:

```bash
cd ~ # volta a home
cd storage/shared/Download/ # onde você deixou o arquivo.
cp type_proot_install.zip ~ # copia para home do termux
```

## AGORA, COM O ARQUIVO NA HOME DO TERMUX:

```bash
cd ~
pkg install -y unzip
unzip type_proot_install.zip
```

## ISSO DEVE CRIAR ALGUNS DIRETÓRIOS NA SUA HOME, LISTE ELES ASSIM:

cd ~
ls .type_proot_install

## AGORA NAVEGUE ATÉ O DIRETÓRIO OCULTO LISTADO:

```bash
cd ~
cd .type_proot_install
```

## DE PERMISSÃO E EXECUTE O SCRIPT PRINCIPAL:

```bash
chmod +x * # dá permissão de execução a todos os arquivos não ocultos nesse diretório.
./type_proot_install.txt # executa o script usando o diretório atual.
```

# EXEMPLOS PRÁTICOS DE COMO USAR DE FORMA RÁPIDA:

## A BARRA INVERTIDA TEM PROPRIEDADES E UMA DELAS É PARA QUEBRAR LINHAS E CONTINUAR O COMANDO COMO SE ESTIVESSE NA MESMA LINHA.
## OPERADORES FAZEM O PAPEL DE LER A SAÍDA DE ERRO, SE FOR POSITIVO "&&" OU SE FOR NEGATIVO "||", ENTÃO ALGO DEVE OU NÃO ACONTECER.

```bash
cd ~/storage/shared/ADownload/PROOT-2/FUNCIONAIS/FUNCIONA-2.9/ &&\
 cp list_install.zip ~ && cd ~ &&\
 unzip list_install.zip &&\
 chmod +x list_install.txt && ./list_install.txt
```

## AGORA NA PRÁTICA NESTE CASO ESPECÍFICO, USAREMOS UM ARGUMENTO PERSONALIZADO DE EXEMPLO.
### o "box" a frente do "type_proot_install.txt" é um argumento e executamos assim:

```bash
cd ~/storage/shared/Download/ &&\
 cp type_proot_install.zip ~ && cd ~ &&\
 pkg install -y unzip && unzip type_proot_install.zip &&\
 cd ~/.type_proot_install && chmod +x * &&\
 ./type_proot_install.txt box && echo "sucedido" || { echo "falso, encerrar"; exit 1; }
```

> [!NOTE]
> **Isso deve ser suficiente para ter uma base simplificada disso.**
> **Acesse meu releases se tiver interesse.**

## Dúvidas comuns:

---

1. Comando 'apt-get update' está reclamando de não haver mirros ou repositórios disponíveis?
Normalmente re-atualizar os repositórios/mirrors resolve o erro.
2. Como fazer? **Execute isso:**
```bash
termux-change-repo 
# [*] All mirrors selected
```
Deverá abrir uma tela interagivel, se estiver marcado **[*] All mirrors selected**, então não mexa, apenas aperte 'Enter' se certificando que essa mesma opção esteja marca sempre. Após isso, ele atualizará os "mirros" atuais do seu Termux.

3. E se não funcionar?
Se o método acima **não resolver**, então você terá que resolver manualmente. Procure na internet.

> [!NOTE]
> O problema não é um mirror problemático, É um mirror antigo que na maioria dos casos foi desprovido do status "ativo".

***
