# Variáveis presentes nos códigos e os seus usos (Working)

### Utilitários

A variável ``utils`` abaixo se encontra na primeira linha de todos os scripts e é responsável por fazer a chamada do script mestre que contém todas as funções utilizadas no curso.
É possível acessar esse script pelo [**link**](https://code.earthengine.google.com/fa8f980b77fcbe151f54bd4727f7f26e), porém é recomendado ter conhecimento prévio de programação na plataforma caso haja interesse em se aventurar nesse código.

```JavaScript

var utils = require('users/vieiramesquita/LAPIG-GEE:CURSO_GEE_LAPIG/UTILITARIOS')

```

### Satélites disponíveis

A variável ``satelite`` demonstrada abaixo é reponsável pela seleção do tipo de dado orbital que pode ser utilizado no curso. Para saber quais dados estão disponíveis, vá ao final da página e maximize seção chamada **"Opções de satélites/sensores/produtos, realces e datas"**

```JavaScript

var satelite = 'MOD13';
var satelite = 'L5_TOA';
var satelite = 'S2';
Bar satelite = 'S2_SR'

```

### Realces de imagem pré-definidos

Para definir as paletas de cores ou composições de visualização é necessário editar a ``realce``. Para saber quais paletas ou composições podem ser utilizadas, vá ao final da página e maximize seção chamada **"Opções de satélites/sensores/produtos, realces e datas"**. A descrição dos realces pode ser encontrada na seção **"Glossário"** encontrada na [página principal](https://github.com/vieiramesquita/LAPIG-GEE).

```JavaScript

var realce = 'OIL';
var realce = 'False';
var realce = 'CHUVA';

```

### Datas iniciais e finais de séries temporais

No Earth Engine cada dado, ou série de dados, possui uma informação referente a data que possibilita a filtragem das informações para períodos restritos. O sistema de datas utilizado na plataforma é o americano (Ano-Mês-Dia) como demonstrado nas variáveis ``data_inicial`` e ``data_final`` abaixo.

```javascript

var data_inicial = '2016-01-01';
var data_final = '2016-12-31';

```

### Selecionar bandas específicas para exportação

É possível filtrar as bandas que você deseja exportar modificando a variável ``bandas`` como nos exemplos abaixo. Caso você queira exportar todas as bandas de um dado basta deixar a variável como no primeiro exemplo. Você pode acessar banco de dados do Earth Engine para saber quais bandas você pode exportar ou acessar o console do Code Editor e clicar na aba de bandas da sua imagens de interesse.

```javascript

var bandas = ['']
var bandas = ['B1','B2','B3']
var bandas = ['B4','B3','B1']
var bandas = ['NDVI']
var bandas = ['ET','PET']

```

### Indicar diretório de exportação

É necessário indicar para onde os dados serão exportados (Google Drive, Assest ou Google Cloud). Para isso você precisa indicar na variável ``diretorio_destino`` em qual o diretório será salvo os seus dados. Para exportar as informações basta clicar na aba "**Task"** e exportar os dados.

```javascript

var diretorio_destino = 'GOOGLE_GEE_DIR'

```

### Visualizar a partir de Coordenada específica

Em alguns scripts é possível centrar a visualização removendo os comentários das variáveis ``lon``  e ``lat``, e habilitando os argumentos de **"lat"** e **"long"** na função de requisição.

Ex.: ``utils.recuperarImagens(satelite, realce, data_inicial, data_final, diretorio_destino, bandas, **lat**, **lon**,mascarar_nuvens)``

```javascript

var lon = -61.0236
var lat = 2.5502

```

### Aplicar máscaras vetoriais

A variável ``mascara`` é utilizada para armazenar os vetores necessários para delimitar a área de interesse. Esse curso traz alguns vetores já precarregados no Earth Engine. É possível realizar o upload de um Shapefile utilizá-lo a partir do seu **ID** como no primeiro exemplo.

```javascript

var mascara = ee.FeatureCollection("users/lealparente/matopiba");
var regiao = utils.vetores.biomas.filter(ee.Filter.eq('NM_BIOMA','PANTANAL'))

```


### Filtrar nuvens, ruídos e "_Bad Data_"

Alguns scripts possuem a função de filtrar a parir de dados de qualidade de pixel como mostrado abaixo. Esse filtro é habilitado nativamente na maioria dos processamentos realizados durante o curso. 

```javascript

var mascarar_nuvens = false

```

### Filtros redutores de séries

A variável ``redutor`` tem como objetivo aplicar a função redutora escolhida. Você pode encontrar mais funções redutoras, como as representadas abaixo, na aba **"Docs"** na seção **"ee.Reducer"**.

```javascript

var redutor = ee.Reducer.median()
var redutor = ee.Reducer.min()
var redutor = ee.Reducer.max()
var redutor = ee.Reducer.sdtDev()

//Pode ser encontrada também com o nome de "filtro"

var filtro = ee.Reducer.median()
var filtro = ee.Reducer.min()
var filtro = ee.Reducer.max()
var filtro = ee.Reducer.sdtDev()

```

### Adicionar sufixo ao nome do dado exportado

Através da variável ``nome_sufixo`` é possível inserir um sufixo no nome do arquivo a ser exportado.

```javascript

var nome_sufixo = 'MEDIA_BR_PRECP'
var nome_sufixo = 'MIN_LAI_SECA'
var nome_sufixo = 'MEDIANA_BRASIL'

```

### Recortar dados por região de interesse (ROI)

Para habilitar o recorte de dados utilizando a variável ``mascara`` é necessário deixar como ``true`` (Verdadeiro) a variável ``clip``.

Ex.: ``utils.gerarMosaicos(satelite, realce, data_inicial, data_final, diretorio_destino, mascara, nome_sufixo, **clip**)``

```javascript

var clip = true //Habilita o recorte
var clip = false //Desbilita o recorte

```

### Desabilitar/Habilitar centralização/reset de visualização (BETA)

Em alguns casos a centralização de visualização pode atrapalhar nas análises visuais dos dados. Pensando em otimizar esse problema, foi criada a variável ``centerVis`` com o objetivo de habilitar/desabilitar a centralização/reset de visualização.

```javascript

var centerVis = true

```

### Cáculos de índices ou expressões

Os scripts que trabalham com o uso de índices espectrais fazem uso das variáveis ``expressao`` e ``expressao_realce``, porém estas variáveis devem conter outras que fazem referência as expressões matemáticas, limite de realce e paletas de cores como demonstrado abaixo nas variáveis ``LAI_1`` e  ``LAI_1_REALCE``.

```javascript

var LAI_1 = "(-1)*log(((0.69 - (((NIR - RED)*(1+0.5))/(SWIR1 + RED + 0.5)))/0.59)/0.91)"
var LAI_1_REALCE = { min: -0.05,
                     max: 0.30,
                     palette:['#FFFFFF','#CE7E45','#DF923D','#F1B555','#FCD163','#99B718','#74A901' ,'#66A000','#529400','#3E8601','#207401','#056201','#004C00','#023B01','#012E01','#011D01','#011301']
                     }
var expressao = LAI
var expressao_realce = LAI_REALCE

```

É possível encontrar alguns índices disponíveis nos próprios scripts e suas referências na seção **"Índices Espectrais"** na [página principal](https://github.com/vieiramesquita/LAPIG-GEE).

Você pode encontrar também mais paletas de cores através deste [link](https://github.com/gee-community/ee-palettes).

### Filtros de estatística de área

Assim como os filtros de redução de séries temporais, os filtros estatísticos fazem uso das mesmas funções. Porém nesse caso é possível combiná-los como mostrado no segundo exemplo da variável ``estatística``.

```javascript

var estatistica = ee.Reducer.median()

var estatistica = ee.Reducer.min()
                 .combine(ee.Reducer.max(), null, true)
                 .combine(ee.Reducer.mean(), null, true)

```

---------------

<details>
<summary> <b>Opções de satélites/sensores/produtos, realces e datas</b> </summary>
<p>

### [TRMM 3B43 V7 (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/TRMM_3B43V7)
    var satelite = 'TRMM' 
    var realce = 'Chuva' 
    var data_inicial = '1998-01-01'
    var data_final = 'Atual'

### [ALOS DEM 30M (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/JAXA_ALOS_AW3D30_V1_1)
    var satelite = 'ALOS' 
    var realce = 'ALT' 
Não necessita de data_inicial e/ou data_final

### [SRTM V4 30M (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003)
    var satelite = 'SRTM' 
    var realce = 'ALT' 
Não necessita de data_inicial e/ou data_final

### [MOD11A2 TEMPERATURA DE SUPERFICIE (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD11A1)
    var satelite = 'MOD11' 
    var realce = 'TEMP' 
    var data_inicial = '2000-03-05'
    var data_final = 'Atual'

### [MOD13Q1 INDICE DE VEGETACAO (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD13Q1)
    var satelite = 'MOD13' 
    var realce = 'NDVI' ou 'EVI' ou 'Agri'
    var data_inicial = '2000-02-18'
    var data_final = 'Atual'

### [MOD16A2 EVAPOTRANSPIRACAO (GLOBAL)](https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD16A2)
    var satelite = 'MOD16' 
    var realce = 'ET' ou 'PET'
    var data_inicial = '2000-01-01'
    var data_final = 'Atual' 

### [LANDSAT 5 TOA](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LT05_C01_T1_TOA) ou [LANDSAT 5 SR](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LT05_C01_T1_SR)
    var satelite = 'L5_TOA' ou 'L5_SR'
    var realce = 'Agri' ou 'False' ou 'True'
    var data_inicial = '1984-03-01'
    var data_final = 2012-05-05

### [LANDSAT 7 TOA](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LE07_C01_T1_TOA) ou [LANDSAT 7 SR](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LE07_C01_T1_SR)
    var satelite = 'L7_TOA' ou 'L7_SR'
    var realce = 'Agri' ou 'False' ou 'True'
    var data_inicial = '1999-01-01'
    var data_final = 'Atual' 

### [LANDSAT 8 TOA](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC08_C01_T1_SR) ou [LANDSAT 8 SR](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC08_C01_T1_SR)
    var satelite = 'L8_TOA' ou 'L8_SR'
    var realce = 'Agri' ou 'False' ou 'True'
    var data_inicial = '2013-04-11'
    var data_final = 'Atual' 

### [SENTINEL 1A & 1B SAR GRD](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD) 
    var satelite = 'S1' 
    var realce = 'SAR' 
    var data_inicial = '2014-10-03'
    var data_final = 'Atual'

### [SENTINEL 2A & 2B TOA](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2)
    var satelite = 'S2' 
    var realce = 'Agri' ou 'False' ou 'False20' ou 'True'
    var data_inicial = '2015-06-23 '
    var data_final = 'Atual'

### [SENTINEL 3 OLCI](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S3_OLCI)
    var satelite = 'S3'
    var realce = 'False' ou 'True'
    var data_inicial = '2016-10-18'
    var data_final = 'Atual'

</p>
</details>
