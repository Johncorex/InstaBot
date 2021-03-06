
![N|Solid](https://i.imgur.com/33xjIQf.jpg)

# InstaBot - Selenium + Scrapy

Bot para automatizar curtidas e comentários usando Selenium e Scrapy! 

- [x] Apenas Curtir fotos.
- [x] Apenas Comentar em fotos.
- [x] Curtir e Comentar em fotos.
- [x] Possui 2 modos de busca.
    - Hashtags.
    - Seguidores de um perfil.
- [x] Possui um sub-modo que busca por Trending Topics e Hashtags do twitter no Brasil.

*Pretendo adicionar mais funcionalidades e construir uma interface gráfica futuramente!*

# Sumário:
    
   - [Preparando o ambiente](#preparando-o-ambiente)
        - [Linux](#linux)       
        - [Windows](#windows)
        
   - [Utilizando!](#utilizando)
   
   - [Desempenho do Bot!](#desempenho-do-bot)
   
   - [Observações](#observações)

# Preparando o ambiente:

*\*Os passos com 'ou' representam possíveis soluções para problemas que possam vir a ocorrer, caso a primeira opção não funcione.*

## Linux:
   - Atualize o sistema.
   ```sh
sudo apt-get update 
```

   - Atualize o pip.
   ```sh
pip install --upgrade pip 

ou 

pip3 install --upgrade pip
```

  - Instale o Selenium.
   ```sh
pip install selenium

ou

pip3 install selenium
```
  - Instale o Scrapy.
   ```sh
pip install scrapy

ou

pip3 install scrapy
```

  - Baixe o Webdriver referente ao navegador: [Chrome](https://chromedriver.chromium.org/downloads) ou [Firefox](https://github.com/mozilla/geckodriver/releases).
    - Certifique-se de que a versão do Webdriver é compatível com a do seu navegador!
    - Caso tenha problema com algum navegador, tente com outro.
    - **Indico a utilização do Firefox, pois o Chrome apresenta alguns problemas de compatibilidade com o modo 'Comment'.**
  - Mova o Webdriver (apenas o driver e não a pasta!) para:
   ```sh
sudo mv ~/local_do_driver/driver /usr/local/bin

ou

sudo mv ~/local_do_driver/driver /usr/bin

```

   - Abra a pasta que contém o modulo [main_bot.py](https://github.com/drbuche/InstaBot/blob/master/instabot/main_bot.py).
   - Abra o terminal dentro desta pasta e execute os comandos:
   ```sh
sudo chmod +x main_bot.py 

sudo chmod +x scrapy_twitter.py
```


## Windows:

- Baixe o [Python](https://www.python.org/downloads/) e instale (lembre-se de marcar a opção Path).
   
- Atualize o pip no prompt com o comando:
 ```sh
-m pip install --upgrade pip

ou 

pip install --upgrade pip 
```

- Instale o Selenium com o comando:
```sh
pip install selenium
```
- Instale o Scrapy com o comando:
```sh
pip install scrapy
```
- Caso tenha problemas na instalação do Scrapy, você deve baixar o [Anaconda](https://www.anaconda.com/products/individual).
    - Após instalar, abra o Anaconda Prompt (anaconda3) e digite o comando:
```sh
conda install scrapy
```

   - Todos os procedimentos referente aos comandos `Scrapy` do tópidco [Utilizando!](#utilizando) , devem ser realizados dentro deste prompt.
   - Caso preferir, você pode instalar o selenium dentro do Anaconda, após isso você pode realizar todos os comandos do InstaBot dentro deste prompt.

```sh
conda install selenium
```   
    

- Baixe o Webdriver referente ao navegador: [Chrome](https://chromedriver.chromium.org/downloads) ou [Firefox](https://github.com/mozilla/geckodriver/releases).
    - Certifique-se de que a versão do Webdriver é compatível com a do seu navegador!
    - Caso tenha problema com algum navegador, tente com outro.
    - **Indico a utilização do Firefox, pois o Chrome apresenta alguns problemas de compatibilidade com o modo 'Comment'.**
    - Mova o Webdriver (apenas o driver e não a pasta!) para a pasta que contém o modulo [main_bot.py](https://github.com/drbuche/InstaBot/blob/master/instabot/main_bot.py).




# Utilizando!
- 1 – Em [main_bot.py](https://github.com/drbuche/InstaBot/blob/master/instabot/main_bot.py) coloque as referências na lista (*você pode abri-lo com qualquer Notepad ou utilizando uma IDE*) .
    - Caso a busca seja feita for hashtags, coloque as hashtags que deseja realizar a busca dentro da lista 'hashtags' ou, caso opte por Trending Hashtags,  certifique-se de ter realizado o scraping (passo 2.5).
    - Caso prefira realizar o processo em seguidores de um perfil especifico, preencha a lista ‘perfis’ com os perfis que deseja interagir. Isso fará com que você interaja com os 120 últimos seguidores deste perfil.

- 2 – Coloque os comentários que deseja comentar nas respectivas listas:

	- **primeira_palavra**: Será sempre o primeiro elemento da sentença.
	- **complemento**: Pode ser o elemento logo após a 'primeira_palavra' ou ser o primeiro elemento da sentença, com um emoji logo em seguida.
	- **emoji**: Emoticon que será sempre o último elemento da sentença.
	    - **Obs: Emoticons não costumam funcionar no Chrome, apenas no Firefox.* 	
	- **Estas listas servem para criar frases aleatórias, unindo elementos distintos de forma randomica para cada comentário. Quanto mais palavras em cada grupo melhor!**

- 2.5 - Se optou por utilizar o modo 'Trending Hashtags', precisamos realizar o scraping manualmente:
    - Abra o terminal na pasta que contém o [scrapy_twitter.py](https://github.com/drbuche/InstaBot/blob/master/instabot/scrapy_twitter.py)
    - Digite o comando:
```sh
scrapy runspider scrapy_twitter.py
```
		        	
- 3 – Abra o terminal dentro da pasta que contenha o arquivo [main_bot.py](https://github.com/drbuche/InstaBot/blob/master/instabot/main_bot.py) e use o comando:
 
- Linux:
```sh
./main_bot.py
```

- Windows:
```sh
cd C:\Users\etc\etc\até_o_local_do_main_bot.py

python main_bot.py
```

- 3.5 Caso tenha algum problema com a execução do python, altere a primeira linha do modulo [main_bot.py](https://github.com/drbuche/InstaBot/blob/master/instabot/main_bot.py) para:
    
 ```sh
#!/usr/bin/env python 

ou

#!/usr/bin/env python3 
```
- 4 – ?????
- 5 – profit!

# Desempenho do Bot!

- Criei uma conta do zero, coloquei algumas fotos e segui alguns grupos de bandas, jogos, etc...

- Até o momento, com 8 dias de uso, a conta saiu do ZERO e está com:
    - **205 Seguidores.**
    - **711 Likes nas fotos.**
    - **30 comentários em fotos.**
    - **Mais de 30 mensagens no Direct.**

  
<p align="center">
  <img src="https://i.imgur.com/6SsM3FR.jpg">
</p>  

- O Bot está rodando nesta conta desde o dia 11 de setembro. (8 dias de uso)
- Estou rodando o Bot de 6-8h por dia.
- Utilizo no modo **"comentar + curtir"** em **seguidores de perfis**.
- Para interagir com os últimos 120 seguidores do perfil, procuro por perfis que tem em média 15 a 50 mil seguidores. (perfis com mais de 100 mil seguidores são bons, mas costumam ter muitas contas fake...)
    - Seleciono perfis que tem um nicho parecido com o perfil da minha conta do instagram.


![N|Solid](https://i.imgur.com/IjinG9z.jpg)  ![N|Solid](https://i.imgur.com/FVo2fb7.jpg)



# Observações:
- **Durante a execução, você terá a opção de selecionar o Webdriver que deseja utilizar, além de selecionar o idioma do navegador.**
    - **Certifique-se de que escolheu a opção de idioma compatível com seu navegador, assim como a do Webdriver**
- **O bot exibira uma mensagem contendo a hashtag/perfil atual e a data/hora que inciou o ciclo em cada referência. Também atualizará o número de perfis/hashtags totais que já foram interagidos e data/hora que os finalizou.**
- **Modo apenas like: Da like em 1 foto a cada 1-2 min.**
- **Modo apenas comentar: Comenta 1 foto a cada 6-10min**
- **Modo like e comentar:**
	- *No modo hashtags – Da like a cada 1-2 min e comenta 1x a cada 10 fotos.*
	- *No modo perfil – Comenta a cada 10 fotos e da like em 3-6 fotos de cada perfil.*
- **Modo Trending Hashtags coleta o top 5 das últimas 24h no twitter.**
    - Repita o passo 2.5 do tópico [Utilizando!](#utilizando) sempre que desejar atualizar a lista de # do dia. Caso contrario, ele mantera as # antigas. 
    - *Ele cria um arquivo chamado [top_5_hashtags_do_dia.txt](https://github.com/drbuche/InstaBot/blob/master/instabot/top_5_hashtags_do_dia.txt), que armazena as # utilizadas na ultima execução. Este arquivo é sobrescrito a cada execução*
- **Use bot com bom senso, como se ele imitasse uma pessoa real. Sugiro rodar entre as 7h da manhã até as 00 horas, em um período de 3-8 horas por dia, deixe alguns dias sem utilizar, etc...**
- **O tempo entre os comentários no modo like+comentar ainda está em teste.**
- **Caso tenha o erro 'Failed to Load.' e não consiga carregar fotos e perfis, tente apagar o arquivo 'geckodriver.log' dentro da pasta instabot, ele é gerado automaticamente ao executar o aplicativo. Além disso, limpe os cookies dos navegadores e certifique-se que não possui outros dispositivos acessando sua conta ao mesmo tempo pelo navegador.** 