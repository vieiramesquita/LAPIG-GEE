![Vinícius Mesquita](Logo.png)
Laboratório de Processamento de Imagens e Geoprocessamento (LAPIG/UFG) - https://www.lapig.iesa.ufg.br/

--------------
# Introdução ao Processamento em nuvem atráves da plataforma Google Earth Engine
--------------

### Agradecimentos
- Equipe LAPIG
- Iniciativa Mapbiomas
- Universidade Federal de Goiás
- Google / Earth Engine Team

------

### Pré-requisito

- Conhecimentos prévios de Sensoriamento Remoto e Sistemas de Informação Geográfica (SIG)
- Vincular/Registrar a conta do Gmail ao Google Earth Engine: [Earth Engine account registration](https://signup.earthengine.google.com/)
- Adicionar o repositório de scripts GEE do LAPIG ([Basta apenas acessar este link uma vez](https://code.earthengine.google.com/?accept_repo=users/vieiramesquita/LAPIG-GEE)) 

-------------

### Recomendado

- [Realizar tutoriais da Google](https://developers.google.com/earth-engine/tutorial\_js\_01)

--------------

### Introdução

.

---------------

### S01 - [Recuperar Imagens Orbitais](https://code.earthengine.google.com/689f6ca00042d114b10813eba2035fc8)


### S02 - [Aplicar Funções Redutoras](https://code.earthengine.google.com/6530a143b510209b0caace162931739c)


### S03 - [Gerar Mosaicos Livres de Nuvem](https://code.earthengine.google.com/7fb8756e59e06809696b6e04f9d495da)


### S04 - [Gerar Mosaicos Sintetizados](https://code.earthengine.google.com/956b985eedd7d8391ec5af39cb3a7d72)


### S05 - [Gerar Mosaicos de Índices Livres de Nuvem](https://code.earthengine.google.com/a6fb6071301f35a2f9977eb2dcfe2c65)


### S06 - [Gerar Mosaicos Sintetizados de Índices](https://code.earthengine.google.com/a6fb6071301f35a2f9977eb2dcfe2c65)


### S07 - [Gerar Estatística de Zona em dados Sintetizados](https://code.earthengine.google.com/fcdd95dfaf682daf2c99d523472970cd)


### S08 - [Gerar Estatística de Zona em dados Sintetizados de Índices](https://code.earthengine.google.com/c31c81258282cd037c6675c4c0733860)


### S09 - [Gerar Estatística de Zona em Áreas de Pastagem](https://code.earthengine.google.com/5fe4127d63ff87021faf688ec6641512)


### S10 - [Classificação utilizando Random Forest](https://code.earthengine.google.com/327cf98ff134314a7c9c72975f113b17)

---------------

<details>
<summary> <b>Variáveis</b> </summary>
<p>

#### [Você pode aprender mais sobre as variáveis e como edita-las clicando aqui](link)

----

</p>
</details>
---------------

<details>
<summary> <b>Glossário</b> </summary>
<p>
 
* **TOA**: Reflectância de topo de atmosfera
* **SR**: Reflectância de superficie
* **Chuva**: Coloração padrão do dado. e.g. precipitação em mm/h
* **ALT**: Altitude/Elevação em metros
* **TEMP**: Temperatura de Superfície (LST)
* **NDVI**: Índice de vegetação com diferença normalizada (Nir-Red / Nir+Red)
* **EVI**: Índice de vegetação melhorado (2.5 * (Nir - Red)/ 1 + Nir + 6*Red + 7.5*Blue)
* **ET/PET**: Evapotranspiração total / Evapotranspiração potencial total em mm
* **Agri**: Compoisção colorida utilizada na detecção de áreas agrícolas (Swir/Nir/Red)
* **False**: Compoisção colorida utilizada para dar ênfase a vegetação (Nir/Swir/Red ou Nir/Red/Green)
* **False20**: Semelhante ao 'False', porém realiza a composição com as bandas de 20m de Sentinel 2
* **True**: Compoisção colorida que reproduz as cores "naturais" (Red/Green/Blue)
* **SAR**: Diferença de eixo de polarizacao (Radar - VV,VH,VH)
* **OIL**: Visualização da polarização VV (Radar) com realce específico para vazamentos de óleo

</p>
</details>


---------------


<details><summary> <b>Índices</b> </summary>
 
<p>

#### Você pode encontrar mais índices aqui: https://www.indexdatabase.de

----

* **ARI_1** & **ARI_2** : _Anthocyanin Reflectance Index_ - Aplicação:
  * Gitelson, A., M. Merzlyak, and O. Chivkunova. **Optical Properties and Nondestructive Estimation of Anthocyanin Content in Plant Leaves**. Photochemistry and Photobiology 71 (2001): 38-45.
  * https://www.harrisgeospatial.com/docs/LeafPigments.html
----

* **CAI** : _Cellulose Absorption Index_ - Aplicações:
  * Nagler, Pamela & Daughtry, Craig & Goward, Samuel. (2000). **Plant Litter and Soil Reflectance**. Remote Sensing of Environment. 71. 207-215. 10.1016/S0034-4257(99)00082-6.
  * Nagler, P. L., Inoue, Y., Glenn, E. P., Russ, A. L., & Daughtry, C. S. T. (2003). **Celluloseabsorption index (CAI) to quantify mixed soil–plant litter scenes**.Remote Sensing of Environment,87, 310–325.
  * Guerschman, J. -P., Hill, M. J., Barrett, D. J., Renzullo, L., Marks, A., & Botha, E. (2009). **Estimating fractional cover of photosynthetic vegetation, non-photosynthetic vegetationand soil in mixed tree–grassvegetationusing the EO-1 and MODIS sensors**. RemoteSensing of Environment,113,928–945.
----

* **CRI1** & **CRI2** : _Carotenoid Reflectance Index_ - Aplicação:
  * Gitelson, A., et al. **Assessing Carotenoid Content in Plant Leaves with Reflectance Spectroscopy**. Photochemistry and Photobiology 75 (2002): 272-281.
  * https://www.harrisgeospatial.com/docs/LeafPigments.html
----

* **EVI_1** : _Enhanced Vegetation Index_ - Aplicações:
  * Huete, A.; Didan, K.; Miura, T.; Rodriguez, E. P.; Gao, X.; Ferreira, L. G. **Overview of the radiometric and biophysical performance of the MODIS vegetation indices**. Remote Sensing of Environment 83(2002) 195-213
----

* **EVI_2** : _Enhanced Vegetation Index 2_ - Aplicações:
  * Jiang, Z.; Huete, A.R.; Didan, K.; Miura, T. **Development of a two-band enhanced vegetation index without a blue band**. Remote Sens. Environ., 112 (2008), pp. 3833-3845
----

* **LAI_1** & **LAI_2** : _Leaf Area Index_ - Aplicações:
  * Faris, A.A.; Reddy, Y.S. **Estimation of urban heat island using Landsat ETM+ imagery at Chennai city – a case study**. Int. J. Earth Sci. Eng., 3 (2010), pp. 332-340
  * Boegh, E., H. Soegaard, N. Broge, C. Hasager, N. Jensen, K. Schelde, and A. Thomsen. **Airborne Multi-spectral Data for Quantifying Leaf Area Index, Nitrogen Concentration and Photosynthetic Efficiency in Agriculture**. Remote Sensing of Environment 81, no. 2-3 (2002): 179-193.
  * https://www.sciencedirect.com/science/article/pii/S1110982315000551
----

* **MSI** : _Moisture Stress Index_ - Aplicações:
  * Hunt, E.R. and Rock, B.N. 1989. **Detection of changes in leaf water content using near- and middle-infraredreflectances**. Remote Sensing of Environment, 30, 43–54.
----

* **NDBI** : _Normalized Difference Build-up Index_ - Aplicações:
  *  Zha, Y.; Gao, J. ; Ni, S. (2003) **Use of normalized difference built-up index in automatically mapping urban areas from TM imagery**, International Journal of Remote Sensing, 24:3, 583-594, DOI: 10.1080/01431160304987 
----

* **NDII** : _Normalized Difference Infrared Index_ - Aplicações:
  * Hardisky, M. A., Klemas, V., & Smart, R. M. (1983). **The influences of soil salinity, growthform, and leaf moisture on the spectral reflectance ofSpartina alternifloracanopies**.Photogrammetric Engineering and Remote Sensing,49,77–83.
----

* **NDVI** : _Normalized Difference Vegetation Index_ - Aplicações:
  * Rouse, J., R. Haas, J. Schell, and D. **Deering. Monitoring Vegetation Systems in the Great Plains with ERTS**. Third ERTS Symposium, NASA (1973): 309-317.
  * Tucker, C.J.; Elgin, H.J.-Jr.; McMurtrey, J.E.I.; Fran, C.J. **Monitoring corn and soybean crop development with hand-held radiometer spectral data**. Remote Sens. Environ., 8 (1979), pp. 237-248, 10.1016/0034-4257(79)90004-X
----

* **NDWI_1** & **NDWI_2** : _Normalized Difference Water Index_ - Aplicações:
  * **Conteúdo de Água nas folhas** (NDWI_1): Gao, B. **NDWI — A normalized difference water index for remote sensing of vegetation liquid water from space**. Remote Sensing of Environment, 58 (1996), pp. 257-266
  * **Água no ambiente** (NDWI_2):  McFEETERS, S. K. (1996). **The use of the Normalized Difference Water Index (NDWI) in the delineation of open water features**, International Journal of Remote Sensing, 17:7, 1425-1432, DOI: 10.1080/01431169608948714 
----

* **PRI** : _Photochemical Reflectance Index_ - Aplicações:
  * Penuelas, J., I. Filella, and J. Gamon. **Assessment of photosynthetic radiation-use efficiency with spectral reflectance**. New Phytologist 131 (1995): 291-296.
  * Gamon, J., L. Serrano, and J. Surfus. **The Photochemical Reflectance Index: An Optical Indicator of Photosynthetic Radiation Use Efficiency Across Species, Functional Types and Nutrient Levels**. Oecologia 112 (1997): 492-501.
  * https://www.harrisgeospatial.com/docs/LightUseEfficiency.html
----

* **PSRI** : _Plant Senescence Reflectance Index_ - Aplicações:
  * Marsett, R. C., Qi, J. G., Heilman, P., Biedenbender, S. H., Watson, M. C., Amer, S., et al.(2006).**Remote sensing for grassland management in the arid Southwest**. RangeEcology and Management,59, 530–540
  * https://www.harrisgeospatial.com/docs/LightUseEfficiency.html
----

* **PSSR** : _Pigment Specific Simple Ratio_ - Aplicações:
  *  Blackburn, G. A. (1998). **Spectral indices for estimating photosynthetic pigment concentrations: A test using senescent tree leaves**, International Journal of Remote Sensing, 19:4, 657-675, DOI: 10.1080/014311698215919 
----

* **RGR** : _Red-Green Ratio_ - Aplicações:
  * Gamon, J., and J. Surfus. **Assessing Leaf Pigment Content and Activity With a Reflectometer**. New Phytologist 143 (1999): 105-117.
  * Sims, D. A., & Gamon, J. A. (2002). **Relationships between leaf pigment content andspectral reflectance across a wide range of species, leaf structures and developmentalstages**. Remote Sensing of Environment,81,337–354.
  * https://www.harrisgeospatial.com/docs/LightUseEfficiency.html
----

* **RVSI** : _Red-Edge Vegetation Stress Index_ - Aplicações:
  * Merton, R. N. (1998). **Monitoring community hysteresis using spectral shift analysis and the red-edgevegetation stress index**. Proceedings of the Seventh Annual JPL Airborne Earth Science Workshop.NASA, Jet Propulsion Laboratory, Pasadena, California, USA. 12-16 January 1998.
  * Merton, R., and J. Huntington. **Early simulation results of the ARIES-1 satellite sensor for multi-temporal vegetation research derived from AVIRIS**. NASA Jet Propulsion Lab., Pasadena, CA, 1999. 
----

* **SAVI**: _Soil Adjusted Vegetation Index_ - Aplicações: 
  * Huete, A. R. 1988. **A soil-adjusted vegetation index (SAVI)**. Remote Sensing of Environment, 25, 295–309.
----

* **SATVI** : _Soil Adjusted Total Vegetation Index_ - Aplicações: 
  * Marsett, R. C., Qi, J. G., Heilman, P., Biedenbender, S. H., Watson, M. C., Amer, S., et al.(2006). **Remote sensing for grassland management in the arid Southwest**. RangeEcology and Management,59, 530–540
----

* **SIPI_1** & **SIPI_2** : _Structure Insensitive Pigment Index_ - Aplicações: 
  * Penuelas, J., F. Baret, and I. Filella. **Semi-Empirical Indices to Assess Carotenoids/Chlorophyll-a Ratio from Leaf Spectral Reflectance**. Photosynthetica 31 (1995): 221-230.
  * Blackburn, G. A. (1998). **Spectral indices for estimating photosynthetic pigment concentrations: A test using senescent tree leaves**, International Journal of Remote Sensing, 19:4, 657-675, DOI: 10.1080/014311698215919
  * https://www.harrisgeospatial.com/docs/LightUseEfficiency.html
----

* **VARI** : _Visible Atmospherically Resistant Index_ - Aplicações:
  * Gitelson, A., et al. **Vegetation and Soil Lines in Visible Spectral Space: A Concept and Technique for Remote Estimation of Vegetation Fraction**. International Journal of Remote Sensing 23 (2002): 2537−2562.
  * https://www.harrisgeospatial.com/docs/BroadbandGreenness.html#Visible
----

* **VIG** : _Visible Index Green_ - Aplicações:
  * Gitelson, A.A.; Kaufman, Y.J.; Stark, R.; Rundquist, D. **Novel algorithms for remote estimation of vegetation fraction**. Remote Sens. Environ., 80 (2002), pp. 76-87
 
</p>
</details>

---------------
