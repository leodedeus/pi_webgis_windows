# pi_webgis

## O que é um WebGIS?

Um WebGIS (Sistema de Informação Geográfica na Web) é uma aplicação baseada na web que permite a visualização, análise e manipulação de dados geoespaciais. Ele combina informações geográficas e recursos interativos da web para fornecer uma plataforma poderosa para a tomada de decisões baseadas em localização. Os WebGIS são amplamente utilizados em diversas áreas, como planejamento urbano, gestão de recursos naturais, agricultura, geologia, meio ambiente e muito mais.

## Por que Utilizar um WebGIS?

A utilização de um WebGIS oferece diversas vantagens, incluindo:

- **Acesso Universal**: Como é baseado na web, um WebGIS permite que usuários de diferentes locais acessem e colaborem facilmente em análises geoespaciais.

- **Visualização de Dados**: Oferece a capacidade de visualizar dados geográficos complexos em mapas interativos, tornando mais fácil entender padrões e tendências.

- **Tomada de Decisões Baseadas em Localização**: Permite tomar decisões informadas considerando a localização geográfica, o que é crucial em muitos campos, como logística, marketing e planejamento urbano.

- **Integração de Dados**: Facilita a integração de dados geoespaciais de várias fontes, possibilitando análises mais abrangentes.

- **Compartilhamento de Informações**: Permite compartilhar informações geográficas de maneira eficiente com partes interessadas e o público em geral.

Este projeto, pi_webgis, é uma implementação de um WebGIS usando a estrutura Django e a biblioteca Leaflet para criar mapas interativos na web. Siga as instruções abaixo para configurar e personalizar seu próprio WebGIS com base neste projeto.

## Pré-requisitos

Antes de começar, certifique-se de ter o Python instalado em seu sistema. Você pode fazer isso seguindo os passos abaixo:

1. **Baixar o Python**:
   - Faça o download da versão mais recente do Python no [site oficial](https://www.python.org/downloads/).

2. **Instalação**:
   - Durante a instalação, marque a opção "Adicionar Python ao PATH" para que o Python seja facilmente acessível a partir do terminal.

## Configurando o Projeto

Siga estas etapas para configurar o seu projeto:

1. **Crie uma pasta para o projeto**:
   - Crie uma pasta em um local de sua escolha para armazenar o seu projeto Python.

2. **Crie um Ambiente Virtual**:
   - Abra o terminal e navegue até a pasta do projeto que você acabou de criar. Em seguida, crie um ambiente virtual com o seguinte comando:
     ```
     python -m venv venv
     ```

3. **Ative o Ambiente Virtual**:
   - Ative o ambiente virtual. As instruções podem variar dependendo do seu sistema operacional:
     - **No Windows (PowerShell)**:
       ```
       .\venv\Scripts\Activate.ps1
       ```

4. **Instale o Django**:
   - Com o ambiente virtual ativado, instale o Django usando o seguinte comando:
     ```
     pip install django
     ```

5. **Crie o Projeto Django**:
   - Dentro da pasta do projeto, crie um novo projeto Django com o nome que você desejar. Neste exemplo, estamos usando "setup":
     ```
     django-admin startproject setup .
     ```
     Certifique-se de que o nome do projeto está correto, pois ele será usado nas configurações do projeto.

6. **Execute o Projeto**:
   - Inicie o servidor de desenvolvimento Django com o seguinte comando:
     ```
     python manage.py runserver
     ```
     Você deve ver uma mensagem indicando que o servidor está em execução em http://127.0.0.1:8000/.

7. **Crie um Aplicativo Django**:
   - Para criar um aplicativo em seu projeto, use o seguinte comando (substitua "mapleaflet" pelo nome do seu aplicativo):
     ```
     python manage.py startapp mapleaflet
     ```

## Configurando o Aplicativo e o Mapa Leaflet

Siga estas etapas para configurar o aplicativo e criar um mapa Leaflet:

1. **Crie uma Pasta "Templates"**:
   - Dentro da pasta do aplicativo "mapleaflet", crie uma pasta chamada "templates". Esta pasta será usada para armazenar os modelos HTML.

2. **Crie um Arquivo HTML**:
   - Dentro da pasta "templates", crie um arquivo HTML que representará a página com o mapa Leaflet.

3. **Crie uma Visualização**:
   - No arquivo "views.py" do aplicativo "mapleaflet", crie uma função de visualização que renderize o arquivo HTML criado anteriormente. Por exemplo:
     ```python
     from django.shortcuts import render

     def home(request):
         return render(request, "mapleaflet/home.html")
     ```

4. **Configure as Rotas**:
   - No arquivo "urls.py" do projeto (pasta "setup"), importe a função de visualização e configure uma rota para ela:
     ```python
     from mapleaflet.views import home

     urlpatterns = [
         path('', home),
         # Adicione outras rotas aqui, se necessário.
     ]
     ```

5. **Execute o Projeto Novamente**:
   - Reinicie o servidor de desenvolvimento Django com o comando:
     ```
     python manage.py runserver
     ```

Agora você deve ser capaz de acessar a página com o mapa Leaflet em http://127.0.0.1:8000/. Certifique-se de personalizar seu mapa e aplicativo de acordo com suas necessidades.

---

Este README fornece um guia básico para configurar um projeto Django com um aplicativo que usa Leaflet para criar um mapa da web. Lembre-se de consultar a documentação oficial do Django e do Leaflet para obter informações mais detalhadas e personalizar seu projeto de acordo com suas necessidades específicas.
