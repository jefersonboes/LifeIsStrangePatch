# Life is Strange game patch
Path para corrigir o erro
 "error while loading shared libraries: libCoreFoundation.so.476"
 ao rodar o jogo Life is Strange no Manjaro linux.

- Na sua biblioteca de jogos da Steam localize o jogo Life is Strange 
- Clique com o botão direito e abra a opção *Propriedades*
- Localize e abra o item *Arquivos instalados*
- Clique em *Explorar* para abrir a pasta de instalação do jogo
- Localize o arquivo **LifeIsStrange.sh**
- Abra o arquivo em um edidor de texto e localize a linha:
```console
export LD_PRELOAD="${LD_PRELOAD_ADDITIONS}:${LD_PRELOAD}"
```
- Abaixo dessa linha copie e cole os comandos abaixo:
```console
BASEDIR=$(realpath "$(dirname "$0")")
LD_LIBRARY_PATH="${STEAM_RUNTIME}/pinned_libs_32:\
/usr/lib32:\
/usr/lib:\
${STEAM_RUNTIME}/lib/i386-linux-gnu:\
${STEAM_RUNTIME}/usr/lib/i386-linux-gnu:\
${STEAM_RUNTIME}/lib/x86_64-linux-gnu:\
${STEAM_RUNTIME}/usr/lib/x86_64-linux-gnu:\
${STEAM_RUNTIME}/lib:\
${STEAM_RUNTIME}/usr/lib:\
${BASEDIR}:\
${BASEDIR}/lib/x86_64:\
${STEAM_RUNTIME}/lib/x86_64-linux-gnu:\
${STEAM_RUNTIME}/usr/lib/x86_64-linux-gnu"
```
- Salve o arquivo e execute o jogo pela Steam.

