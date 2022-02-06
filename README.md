# 7wallVideo-i3wm
meio de colocar video como wallpaper no gerenciador de janelas i3wm.
Ainda não está bom, fiz rapido para uso pessoal, mas dá para usar.

o que fiz foi pegar um video e tirar capturas de tela dele e essas imagens usei para ficar alternando-as assim dando a impressão que o video esta rodando mesmo.
Porém, nao ficou muito bom com muitas imagens.

Quem quiser arrumar o script é muito bem vindoooo.


requisitos: 

    ffmpeg feh python3 i3wm
    
fileConfig serve para criar o diretório e os arquivos de imagens do video.

7wallVideo é o app para setar no i3wm ou simplesmente rodar via linha de comando enquanto o terminal estiver aberto rodando o video como plano de fundo.


O arquivo fileConfig irá perguntar algumas infos e vai criar um diretorio e os prints do video.

Caso queira tentar o fileConfig e so responder os input's, apos fazer isso e so  dar permissao de execução para o 7wallVideo e editar o arquivo 7wallVideo com o caminho da pasta das imagens que ele criou, setar uma velocidade para que as imagens mudem, colocar quantidade de imagens que tem na pasta e a add na config do i3 "exec caminho/do/7wallVideo", ex: exec /home/rafael/scripts/7wallVideo.

Recomendo testar o programa 7wallVideo no terminal antes de seta-lo nas config do i3 para ver se esta tudo OK.

OBS: Arquivo "algumas instruções" tem um exemplo de como configurar o 7wallVideo.

depois de setar no i3.conf e só dar lougout e logar de novo que irá funcionar.
Para parar e so comentar a linha que tem o comando no i3.conf e dar lougout e logar de novo.


Para roda o fileConfig
    
    python3 fileConfig ou ./fileConfig
    
Ele tentara criar uma pasta dentro da pasta ~/Imagens/, evite nomes de pastas que ja existem em ~/Imagens/.
Na pasta criada ele ira extrair as imagens do video e vai colocar um arquivo de txt com a quantidade de imagens que tem naquela pasta.



Se o fileConfig der erro:

Recomendo criar voce mesmo os arquivos se o fileConfig der erro, voce terá que apontar no arquivo 7wallVideo o diretorio, o numero de imagens criadas e a velocidade.


OBS: com a velocidade muito rapida o control + c nao pega direito, testei com a velocidade de 0.001 e o control + c so pegou porque fiquei segurando.
Porém com uma velocidade de 0.01 ate 0.005 funciona normal.


Voce pode tirar os prints com o ffmpeg e mover todos eles para uma pasta especifica e depois apontar o caminho no arquivo 7wallVideo.

caso vc queira so editar o arquivo 7wallVideo:
recomendo passar o comando de extrair imagens em uma pasta vazia para nao misturar com outras.
ex:
      
     ffmpeg -i nomedofilme.avi -r 1 -s 608×320 -f image2 Caminho/para/pasta/tmp-%01d.jpg

deixe o nome do arquivo como tmp-%01d.jpg ou voce terá que mudar o nome do arquivo em 7wallVideo.

veja como extrair imagens dos videos em:  

     https://www.vivaolinux.com.br/dica/Convertendo-videos-em-imagens-JPEG-no-Linux

mova todas as imagens para uma pasta especifica de sua preferencia

para ver quantas imagens tem na pasta basta rodar o comando abaixo:
      
    ls diretorio/das/imagens/*.jpg 2>/dev/null | wc -l

apos isso é so editar o arquivo 7wallVideo
recomendo testar no terminal se esta funcionando corretamente e se a velocidade esta boa, para isso rode no terminal o programa 7wallVideo.

depois é só ir na sua config do i3 e setar "exec caminho/do/7wallVideo", ex: exec /home/rafael/scripts/7wallVideo.
config do i3 normalmente fica em ~/.config/i3/conf ou em /etc/i3conf (base debian), recomendo copiar /etc/i3conf para ~/.confi/i3/conf
e editar la na sua home
dê permissao para o arquivo e depois e so dar lougout e logar novamente.
para parar caso vc coloque uma velocidade muito rapida e so comentar a linha com o comando no i3.conf, deslogar e logar novamente. No futuro irei arruamar por isso estou subindo aqui.
