![Vinícius Mesquita](Logo.png)
LAPIG - Laboratório de Processamento de Imagens e Geoprocessamento (LAPIG/UFG) - https://www.lapig.iesa.ufg.br/


<b> <p align="center"> Introdução ao Processamento em nuvem atráves da plataforma Google Earth Engine </p> </b> 

--------------

### Agradecimentos
- Iniciativa Mapbiomas
- Universidade Federal de Goiás
- Google / Earth Engine Team

------

### Pré-requisito

- Conhecimentos prévios de Sensoriamento Remoto e Sistemas de Informação Geográfica (SIG)
- Vincular/Registrar a conta do Gmail ao Google Earth Engine: [Earth Engine account registration](https://signup.earthengine.google.com/)
- Adicionar o repositório de scripts GEE do LAPIG: https://code.earthengine.google.com/?accept_repo=users/vieiramesquita/LAPIG-GEE

-------------

### Recomendado

- [Realizar tutoriais da Google](https://developers.google.com/earth-engine/tutorial\_js\_01)

--------------

### Introdução

.

---------------

### S01 - [Recuperar Imagens Orbitais](https://code.earthengine.google.com/689f6ca00042d114b10813eba2035fc8)

---------------

### S02 - [Aplicar Funções Redutoras](https://code.earthengine.google.com/6530a143b510209b0caace162931739c)

---------------

### S03 - [Gerar Mosaicos Livres de Nuvem](https://code.earthengine.google.com/7fb8756e59e06809696b6e04f9d495da)

---------------

### S04 - [Gerar Mosaicos Sintetizados](https://code.earthengine.google.com/956b985eedd7d8391ec5af39cb3a7d72)

---------------

### S05 - [Gerar Mosaicos Livres de Nuvem de Índices](https://code.earthengine.google.com/a6fb6071301f35a2f9977eb2dcfe2c65)

---------------

### S06 - [Gerar Mosaicos Sintetizados de Índices](https://code.earthengine.google.com/a6fb6071301f35a2f9977eb2dcfe2c65)

---------------

### S07 - [Gerar Estatística de Zona em dados Sintetizados](https://code.earthengine.google.com/fcdd95dfaf682daf2c99d523472970cd)

---------------

### S08 - [Gerar Estatística de Zona em dados Sintetizados de Índices](https://code.earthengine.google.com/c31c81258282cd037c6675c4c0733860)

---------------

### S09 - [Gerar Estatística de Zona em Áreas de Pastagem](https://code.earthengine.google.com/5fe4127d63ff87021faf688ec6641512)

---------------

### S10 - [Classificação utilizando Random Forest](https://code.earthengine.google.com/327cf98ff134314a7c9c72975f113b17)

---------------

### Glossário

* TOA: Reflectancia de topo de atmosfera
* SR: Reflectancia de superficie
* Chuva: Coloracao padrao do dado. e.g. precipitacao em mm/h
* ALT: Altitude/Elevacao em metros
* TEMP: Temperatura de Superficie (LST)
* NDVI: Indice de vegetacao com diferenca normalizada (Nir-Red / Nir+Red)
* EVI: Indice de vegetacao melhorado (2.5 * (Nir - Red)/ 1 + Nir + 6*Red + 7.5*Blue)
* ET/PET: Evapotranspiracao total / Evapotranspiracao potencial total em mm
* Agri: Compoiscao colorida utilizada na deteccao de areas agricolas (Swir/Nir/Red)
* False: Composicao colorida utilizada para dar enfase a vegetacao (Nir/Swir/Red ou Nir/Red/Green)
* False20: Semelhante ao 'False', porém realiza a composição com as bandas de 20m de Sentinel 2
* True: Composicao colorida que reproduz as cores "naturais" (Red/Green/Blue)
* SAR: Diferenca de eixo de polarizacao (Radar - VV,VH,VH)
* OIL: Visualização da polarização VV (Radar) com realce específico para vazamentos de óleo

---------------

### Índices

* **ARI_1** & **ARI_2** : Anthocyanin Reflectance Index - Aplicação: https://www.harrisgeospatial.com/docs/LeafPigments.html
  * Gitelson, A., M. Merzlyak, and O. Chivkunova. **Optical Properties and Nondestructive Estimation of Anthocyanin Content in Plant   Leaves**. Photochemistry and Photobiology 71 (2001): 38-45.
  
* **CAI** : Cellulose Absorption Index - Aplicações:
  * Nagler, Pamela & Daughtry, Craig & Goward, Samuel. (2000). **Plant Litter and Soil Reflectance**. Remote Sensing of Environment. 71. 207-215. 10.1016/S0034-4257(99)00082-6.

* **CRI1** & **CRI2** : Carotenoid Reflectance Index 1 - Aplicação: https://www.harrisgeospatial.com/docs/LeafPigments.html
  * Gitelson, A., et al. **Assessing Carotenoid Content in Plant Leaves with Reflectance Spectroscopy**. Photochemistry and Photobiology 75 (2002): 272-281.
  
* **EVI_1** : Enhanced Vegetation Index - Aplicações:
  * Huete, A.; Didan, K.; Miura, T.; Rodriguez, E. P.; Gao, X.; Ferreira, L. G. **Overview of the radiometric and biophysical performance of the MODIS vegetation indices**. Remote Sensing of Environment 83(2002) 195-213
  
* **EVI_2** : Enhanced Vegetation Index 2 - Aplicações:
  * Jiang, Z.; Huete, A.R.; Didan, K.; Miura, T. **Development of a two-band enhanced vegetation index without a blue band**. Remote Sens. Environ., 112 (2008), pp. 3833-3845
  
* **LAI** : Leaf Area Index (https://goo.gl/2EnggF)
* **MSI** : Moisture Stress Index
* **NDBI** : Normalized Difference Build-up Index
* **NDII** : Normalized Difference Infrared Index

* **NDVI** : Normalized Difference Vegetation Index - Aplicações:
  * Tucker, C.J.; Elgin, H.J.-Jr.; McMurtrey, J.E.I.; Fran, C.J. **Monitoring corn and soybean crop development with hand-held radiometer spectral data**. Remote Sens. Environ., 8 (1979), pp. 237-248, 10.1016/0034-4257(79)90004-X
  
* **NDWI_1** & **NDWI_2** : Normalized Difference Water Index
* **PRI** : Photochemical Reflectance Index
* **PSRI** : Plant Senescence Reflectance Index 
* **PSSR** : Pigment Specific Simple Ratio
* **RGR** : Red-Green Ratio
* **RVSI** : Red-Edge Vegetation Stress Index
* **SATVI** : Soil Adjusted Total Vegetation Index 
* **SIPI_1** & SIPI_2 : Structure Insensitive Pigment Index 
* **VARI** : Visible Atmospherically Resistant Index
* **VIG** : Visible Index Green

---------------
