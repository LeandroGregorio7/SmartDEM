# TSharp-DEM 2m | Super-Resolução Topográfica Cloud, Hidrologia D8 & Motor Smart15

**Author:** Dr. Leandro Gregório ([@LeandroGregorio7](https://github.com/LeandroGregorio7)) — [GeoSmart](https://geosmart.online) | [LinkedIn](https://www.linkedin.com/in/leandrogregoriogeo/)

---

## 🇧🇷 Visão Geral (Português)

**TSharp-DEM 2m** é um WebApp 100% *client-side* (hospedado via GitHub Pages, sem necessidade de instalação de plugins) que realiza o *downscaling* guiado de Modelos Digitais de Elevação (MDEs) de **30 m para 2 m**, fechando a tríade de alta resolução da plataforma **Smart15**:
1. **Rede Viária e POIs (OpenStreetMap)**
2. **Conforto Térmico e Uso/Cobertura da Terra (LST Super-Resolution + Smart OBIA + BARU Validator)**
3. **Microtopografia Urbana a 2 m, Hidrologia D8 e Impedância de Caminhada/Ciclismo de Tobler**

### Funcionalidades Completas Incluídas nesta Versão
- **Mapas Base & Visualização 2D / 3D (ON/OFF):** Alternância entre *Esri World Imagery*, *Mapa Base OSM* e *Esri Topographic*, além de renderizador **3D interativo em WebGL (Three.js)** com controle de exagero vertical (`1.0x` a `5.0x`).
- **Seleção de Área (AOI):** Desenho de Bounding Box diretamente na tela ou importação de polígonos em **`.kml`**, **`.geojson` / `.json`** e **`.shp`**.
- **Variáveis Geomorfométricas a 2 m:**
  - Altitude MDT 2 m *Bare-Earth* vs. MDE 30 m Bruto
  - Declividade (*Slope*)
  - Direção / Orientação de Vertentes (*Aspect* `0°–360°`)
  - Insolação / Radiação Solar Direta (`Wh/m²` com controle de Azimute e Elevação Solar)
  - Velocidade de Caminhada e Ciclismo ([ Equação de Tobler ](https://en.wikipedia.org/wiki/Tobler%27s_hiking_function) para o **Smart15**)
- **Unidades Dinâmicas & 7 Paletas Científicas:** Conversão instantânea entre **Metros (`m`) / Pés (`ft`)** e **Graus (`°`) / Porcentagem (`%`)**, com 7 paletas (*Terrain, Turbo, Viridis, Magma, RdYlGn, Circular HSV e Grayscale*).
- **Hidrologia D8 & Delimitação de Bacias por Exutório (2 m):**
  - Direção de Fluxo D8 (`1` a `128`) e Fluxo Acumulado por ordenação topológica.
  - Extração vetorial automática da rede de drenagem classificada por **Ordem de Strahler** com ajuste de limiar em tempo real.
  - **Delimitação de Bacia Hidrográfica clicando no Exutório (*Pour Point*)**, calculando área em hectares (`ha`) e declividade média.
- **Curvas de Nível Equidistantes (`1 m`, `2 m`, `5 m`, `10 m`):** Extração via *Marching Squares* com distinção entre curvas mestras e intermediárias.
- **Classificação de Relevo da EMBRAPA (SiBCS):** Quadro automático das 6 classes (*Plano, Suave Ondulado, Ondulado, Forte Ondulado, Montanhoso e Escarpado*) com área em `ha` e `%`, exportável em `.csv`.
- **Ferramenta de Perfil Topográfico (A → B):** Traçado interativo em tela comparando o relevo de 30 m vs. 2 m e declividade, com exportação dedicada em `.png`.
- **Exportação Completa de Acordo com a Seleção:**
  - **Rasters:** GeoTIFF Float32 (`.tif`), ESRI ASCII Grid (`.asc`), XYZ Georreferenciado (`.xyz`) e ENVI Binary (`.bil`).
  - **Vetores:** GeoJSON (`.geojson`) e **ESRI Shapefile completo (`.zip` contendo `.shp`, `.shx`, `.dbf` e `.prj`)** para Rede D8, Bacias Hidrográficas e Curvas de Nível.
  - **Relatórios Visuais:** Captura em alta resolução da tela + legenda + paleta de cores (`.png`).
- **Interface Bilíngue (`PT-BR` | `EN`), Modais de Metodologia, Tutorial Rápido e Log de Processamento em Tempo Real.**

---

## 🌐 Overview (English)

**TSharp-DEM 2m** is a standalone, zero-install browser WebApp hosted on GitHub Pages that downscales 30 m elevation models down to **2 m resolution** using optical-guided super-resolution, [ANADEM](https://www.mdpi.com/2072-4292/16/13/2321)/[FABDEM](https://gee-community-catalog.org/projects/fabdem/) bare-earth filtering, and OpenStreetMap road/stream conditioning.

It includes 2D/3D WebGL visualization, KML/GeoJSON/SHP AOI upload, Elevation (`m`/`ft`), Slope (`°`/`%`), Aspect, Solar Insolation, Topographic Profile (`PNG`), Equidistant Contours (`1m–10m`), EMBRAPA Zonal Slope Classification (`CSV`), D8 Flow Direction & Strahler Drainage Network, and Clicked Pour-Point Watershed Delineation — exporting directly to **GeoTIFF (`.tif`)**, **ESRI ASCII (`.asc`)**, **XYZ (`.xyz`)**, **GeoJSON (`.geojson`)**, and **ESRI Shapefile (`.zip`)**.

---

## 🚀 Como Publicar no GitHub Pages / Deployment

1. Crie um repositório público chamado `tsharp-dem-2m` em `https://github.com/LeandroGregorio7`.
2. Suba os arquivos deste pacote (`index.html`, `README.md` e `.github/workflows/deploy.yml`).
3. Em **Settings -> Pages**, selecione a branch `main` (ou `GitHub Actions`) e acesse `https://leandrogregorio7.github.io/tsharp-dem-2m/`.
