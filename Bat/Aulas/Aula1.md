# Entendendo arquivos .bat

Arquivos .bat são arquivos que podem executar qualquer função de terminal

* echo "x" = escreve algo no terminal
* start "nome" "path" = abre algum aplicativo.
* timeout /t x =  seta um tempo para algo acontecer, sendo x o tempo em segundos.

Tem como executar arquivos também com esse start, basta colocar o arquivo. Pelo visto apis, como a Audio() do javascript por serem nativas do HTML, não funcionam no console, então vai de testar o que funciona ou não.

Mas tá ai o script para rodar audio de fundo criando um arquivo:

~~~bat
@echo off
set "file=seuArquivoDeAudio.eAExtensao"
( echo Set Sound = CreateObject("WMPlayer.OCX.7"^)
  echo Sound.URL = "%file%"
  echo Sound.Controls.play
  echo do while Sound.currentmedia.duration = 0
  echo wscript.sleep 100
  echo loop
  echo wscript.sleep (int(Sound.currentmedia.duration^)+1^)*1000) >sound.vbs
start /min sound.vbs
~~~
