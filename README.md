# 
![palera1n-Header](https://user-images.githubusercontent.com/104146035/204871654-854b47a5-866b-41e1-aaab-8059cbfc4b9a.jpg)






Depois de clonar este repositório no seu terminal do seu computador linux, por favor, vá até o site mediafire neste link https://is.gd/LdlOUZ e faça download do arquivo compactado e jogue ele (sem extrair) para dentro da pasta "palera1n-3.0/ramdisk/other/" nos seus arquivos locais, só depois prossiga com o processo de jailbreak.

# This is a work in progress. by [pwnd2e@Twitter](https://twitter.com/pwnd2e) for this modified version of [palera1n](https://github.com/palera1n/palera1n)
Read this throughly, feel free to ask questions, know the risks. 

Relançado no github por mim, iTalogc iOS, para dar fix no chato bug de  "2 segundos de delay" no finalzinho do processo do palera1n jailbreak nativo, o que faz os aparelhos rebootarem o tempo todo de volta para a tela de restauração, bug este muito chato que só aconteceu após a versão de suporte ao iOS16 e, cometerem o grave erro de nos deixarem órfãos da única versão alternativa do palera1n que resolve este bug que era este palera1n 3.0. 
Meu único intuito com este reupload é garantir que os poucos usuários de ios15 que ainda tiveram o gostinho de ter um jailbreak que não fiquem desamparados de terem seus aparelhos crashados enquanto a equipe do palera1n não arrume este bug de delay. Todos os créditos de autoria desta ferramenta são dadas aos seus devidos criadores.


- 1. [open](https://discord.gg/5pWry9wn6p) Ask in r/jailbreak Discord #palera1n channel
- 2. [open](https://discord.gg/4S3yUMxuQH) Ask in palera1n Discord
- 3. [open](https://discord.gg/kKJmDDaZrB) Ask in 2escustomservices Discord #palera1n channel
- 4. Or open a GitHub issue

Please, please, please, provide necessary info:

- iOS version and device (eg. iPhone 7+ 15.1, iPhone 6s 15.3.1)
- Computer's OS and version (eg. Ubuntu 22.04, macOS 12.0 and up)
- The command you ran
- Debug logs with `--debug`



# palera1n

iOS 15.0-15.7.2 **work in progress, tethered** checkm8 "jailbreak" 

# What does this do?

It boots the device with AMFI patches. On first run, it'll boot a ramdisk which dumps your onboard blob, and installs Sileo and Substitute.

**WARNING 1**: I am NOT responsible for any data loss. The user of this program accepts responsibility should something happen to their device. While nothing should happen, jailbreaking has risks in itself. If your device is stuck in recovery, please run `futurerestore --exit-recovery`, or use `irecovery -n`. Using this on iOS 16 has a higher chance of bootlooping you.

On A10 and A11, you **must disable your passcode while in the jailbroken state**. On A10, this can be fixed in the future by implementing blackbird. On A11, we don't have a SEP exploit yet.

# Linux issues
Linux has some weird usbmuxd issues. We have tried our best to fix them, but there stil are issues. We highly recommend to compile and install [usbmuxd2](https://github.com/tihmstar/usbmuxd2).

Stop making issues about Linux not being able to connect, we are aware. This includes being stuck on waiting for ramdisk to finish booting.

# Prerequisites
- 1. checkm8 vulnerable iOS device on iOS 15 (A8X-A11)
    - You must install the Tips app from the App Store before running the script
- 2. Linux or macOS computer
    - Python 3 is required
- 3. iOS 15.0-15.7.2
- 4. A brain
    - Remember, this is mainly for developers.

# How to use
*OBS: no lugar do "15.x.x" nos comandos abaixo bote a mesma versão do ios instalada no seu aparelho

- 1. Clonar este repositório no xfce terminal com o comando `sudo git clone --recursive https://github.com/Italogc/palera1n-3.0 && cd palera1n-3.0`
    - Antes de fazer o jailbreak desative todos os códigos de bloqueio presentes no seu aparelho
    - Botar seu aparelho em modo DFU manualmente antes de fazer o procedimento de jailbreak.
- 2. - For rootless Run `sudo ./palera1n.sh --tweaks 15.x.x`   
   _Para clonar o diretório root: `sudo ./palera1n.sh --tweaks 15.x.x --semi-tethered` 
   - Após fazer o jailbreak semi-tethered, e for refazer o jailbreak, lembre-se de dar "do all" nos ajustes do palera1n
   - se o processo travar pela metade e seu aparelho crashar em modo dfu, execute o comando a seguir para destravar o seu aparelho: `sudo ./palera1n.sh --dfuhelper` 
- 3. Durante a primeira vez que for fazer jailbreak no seu aparelho, você vai ter que copiar e colar as seguintes frases no terminal e dar enter para prosseguir com o procedimento de jailbreak:
    - Quando o terminal solicitar digite:  `Yes, pwn my idevice`  
    - Em seguida, quando o terminal solicitar digite: `Yes, do as I say`

- 4. CASO ACONTEÇA DO JAILBREAK E O APARELHO CRASHAREM EM BOOTLOOP ETERNO COM A FRASE "waiting for connection no connection for 2222->22, fd = 5" NO TERMINAL, ABRA A SEGUNDA JANELA ABERTA DO TERMINAL E DIGITE CADA UM DOS COMANDOS ABAIXO PARA DESCRASHAR O APARELHO DO BOOTLOOP ETERNO. MAS JAMAIS FECHE A OUTRA JANELA DO TERMINAL, POIS O PROCESSO DE JAILBREAK VAI CONTINUAR EM DIANTE NAS DUAS JANELAS JUNTAS AO MESMO TEMPO:

sudo systemctl stop usbmuxd

sudo usbmuxd -f -p

- 5. Caso o processo de jailbreak algum dia crashe seu aparelho, bote seu aparelho em modo DFU você poderá deletar o jailbreak pelos comandos abaixo no terminal:

cd palera1n-3.0

sudo ./palera1n.sh --restorerootfs 15.x.x



# Repos
All repos work because it uses normal Procursus and not rootless.
- [pwnd2e](https://www.2escustomservices.com/iOS15) You can add this repo for tweaks that wont bork your idevice

# Credits


- [pwnd2e](https://github.com/pwnd2e) for this modified fork

- [Nathan](https://github.com/verygenericname)
    - The ramdisk that dumps blobs is a slimmed down version of SSHRD_Script
    - Also helped Mineek getting the kernel up and running and with the patches
    - Helping with adding multiple device support
- [Mineek](https://github.com/mineek)
    - For the patching and booting commands
    - Adding tweak support
- [Amy](https://github.com/elihwyma) for the Pogo app
- [nyuszika7h](https://github.com/nyuszika7h) for the script to help get into DFU
- [the Procursus Team](https://github.com/ProcursusTeam) for the amazing bootstrap
- [F121](https://github.com/F121Live) for helping test
- [tihmstar](https://github.com/tihmstar) for pzb/original iBoot64Patcher/img4tool
- [xerub](https://github.com/xerub) for img4lib and restored_external in the ramdisk
- [Cryptic](https://github.com/Cryptiiiic) for iBoot64Patcher fork


