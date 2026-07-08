# type_proot_install

---

Explicação rápida de como eu instalo meu ambiente gráfico no Termux `(sem root)` em um: `Infinix Hot 30i: ( MT Hélio G37 (MT6765H), Cortex A53 mínimo 400MHz, x4 1,8GHz x4 2.3GHz ) ( OpenGL ES 3.2 build 1.13@5776728, PVR GE8320, Vulkan 1.1, Frequência mínima/padrão da GPU: 650 MHz )`

---

## INSTALE O `TERMUX` APK E O `TERMUX:X11` APK DO `F-DROID` SE POSSÍVEL:
**Opcionalmente instale o `Termux:API`**
https://f-droid.org/pt_BR/packages/com.termux/ e https://github.com/termux/termux-x11/releases e https://f-droid.org/pt_BR/packages/com.termux.api/

> [!NOTE]
> **O 'Termux:X11' só está disponível para 'Android 8.0' ou superior.**
> **Caso esteja em um Android 7.1 ou inferior, recomendo usar VNC no lugar. Mas a experiência não será boa devido a possível latência.**

## APÓS INSTALAR E OPCIONALMENTE PERMITA O ARMAZENAMENTO:
```sh
termux-setup-storage
```

---

## PARA ENTENDER OQUE ESSE REPOSITÓRIO TEM A OFERECER SIGA ESSES PASSOS:

**Na maioria dos casos** eu `recomendo instalar` esses pacotes dentro do `Termux`, pois os scripts desse repositório frequentemente usam eles.
```sh
apt update
pkg install -y wget p7zip file
cd ~
```

## Agora os métodos de adquirir:
```sh
wget -O <file> <url>
curl -L -o <file> <url>
```

## O que faz? Ele te poupa ter que fazer toda a instalação manual desnecessariamente, porém as ainda tem as desvantagens técnicas que citarei:
- > **Vantagens:**
- | Instala o contêiner PRoot:Debian Trixie 13.3 ( se for o atual do proot-distro )
- | Instala após o contêiner box64/86 (versão do ptitSeb), wine 5.21 (stable), winetricks/64 (wrapper)
- | Instala algumas libs e outros recursos estéticos simples que não custaram um tempo significativo
- > **Desvantagens:**
- | A Instalação só contém o Debian, então é limitada
- | Instala o box64/86, mas com uma compilação fraca com flags quase inúteis
- | Instala o Wine com uma versão antiga 5.21, você terá problemas com recursos mais novos
- | Instala o winetricks com funcionamento na gambiarra, e que em um ambiente proot-distro sobre Termux só é útil se você usar Aceleração Vulkan diretamente no contêiner via drivers ou técnicas usando um dispositivo rootado
- | Instala algumas excessões para evitar problemas e uns recursos inúteis mais para ficar um pouco bonito
- <

Dicas lógicas básicas:
A BARRA INVERTIDA `\` TEM PROPRIEDADES E UMA DELAS É PARA QUEBRAR LINHAS E CONTINUAR O COMANDO COMO SE ESTIVESSE NA MESMA LINHA.
OPERADORES FAZEM O PAPEL DE LER A SAÍDA DE ERRO, SE FOR POSITIVO `&&` OU SE FOR NEGATIVO `||`, ENTÃO ALGO DEVE OU NÃO ACONTECER.

---

> [!NOTE]
> **Isso deve ser suficiente para ter uma base simplificada disso.**
> **Acesse meu releases se tiver interesse.**

---

## Versão de teste: 
- Essa versão não faz parte dos releases, porém foi baseada neles. Agora você pode executar logo após instalar o Termux, pois o `curl` é basicamente nativo do Termux.
- Eu diria que esse foi o script mais bem elaborado desse repositório, juntando tudo que já tinha e melhorando oque já existia. Porém ainda tem erros bobos que eu não irei arruma. Desculpe.
```sh
# Dessa vez eu brinquei com o código, hehe..
curl --progress-bar -LO https://raw.githubusercontent.com/diogoeae1/type_proot_install/refs/heads/main/control_install.txt && sh control_install.txt all:local
```
- As flags são essas:
- > **lista de argumentos:**
- | KEYS='sua chave alvo' <- apenas se a chave automática falhar
- | debian <- instala o contêiner debian
- | box <- compila e instala o BOX correspondente 
- | box:local <- instala uma versão de box com o mínimo para funcionar pré-compilada por mim em uma CPU Cortex A53 x8 média 1,9GHz
- | wine <- baixa e instala o wine correspondente ao seu respectivo diretório na sua home. Use os prefixos wine32 e wine64 para evitar resolver quebras
- | winetricks <- instala o winetricks com interceptação ao requisito de diretório
- | apps <- instala algumas dependências, plugins e aplicações básicas
- | apps:extra <- além de apenas instalar aplicações básicas, também instala o chromium com adição de --no-sandbox e libs para explorer do wine
- | style <- instala um tema de janelas com bordas arredondadas
- > **argumentos especiais:**
- | all:local <- instala tudo que o script tem a oferecer usando o argumento local
- | all <- instala tudo que o script fornece só que compila localmente o box64/86
- | log <- auto-explicativo, mostra o conteúdo do arquivo de registro final resumido, mas ele está incompleto
- <

---

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

---
