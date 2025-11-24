# BackLog---Guardi-Verde
Aplicação de IA no monitoramento e controle do desmatamento por meio de imagens de satélites. 
Monitoramento de Desmatamento com Dados Abertos e Inteligência Artificial
Detectando mudanças na floresta em tempo quase real através de análise de imagens de satélite.

🌍 Sobre o Projeto
O Guardiã Verde é uma solução open-source para monitoramento de desmatamento que utiliza inteligência artificial e análise de imagens de satélite Sentinel-2. O projeto visa democratizar o acesso à informação ambiental e contribuir para a redução do desmatamento ilegal no Brasil.
O Desafio

6.288 km² de desmatamento na Amazônia em 2024
652.197 hectares desmatados no Cerrado em 2024
46% das emissões brasileiras vêm de mudanças de uso da terra
Necessidade de monitoramento rápido e eficaz

Nossa Solução:
Pipeline aberto de detecção de mudanças que vetoriza áreas candidatas e publica alertas em mapa interativo, reduzindo a assimetria de informação e permitindo fiscalização eficaz.

Características

🛰️ Imagens de Satélite: Utiliza Sentinel-2 L2A de alta resolução
🔍 Detecção de Mudanças: Análise temporal "antes e depois"
📍 Alertas Georeferenciados: Exportação em formato GeoJSON
📊 Dados Abertos: Integração com PRODES, DETER e MapBiomas
☁️ Processamento em Nuvem: STAC APIs e Cloud Optimized GeoTIFFs
⚡ Baixa Latência: < 48 horas entre aquisição e alerta
🗺️ Visualização Interativa: Mapa web com Leaflet


🚀 Tecnologias
Backend

Python 3.9+
GDAL/Rasterio: Processamento geoespacial
NumPy/Pandas: Análise de dados
Scikit-image: Processamento de imagens
PySTAC-Client: Acesso a catálogos STAC

Frontend

HTML5/CSS3/JavaScript
Leaflet.js: Mapeamento interativo
Bootstrap 5: Interface responsiva

Deploy

Render: Hospedagem da aplicação
GitHub Pages: Documentação

📦 Instalação
Pré-requisitos
bash# Python 3.9 ou superior
python --version

# Git
git --version
Clonar o Repositório
bashgit clone https://github.com/seu-usuario/guardia-verde.git
cd guardia-verde
Instalar Dependências
bash# Criar ambiente virtual (recomendado)
python -m venv venv

# Ativar ambiente virtual
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate

# Instalar dependências
pip install -r requirements.txt

⚙️ Configuração
1. Configurar config.json

   bash cp config.example.json config.json

   ▶️ Execução
Modo Básico
bashpython main.py --config config.json
Com Parâmetros Customizados
bashpython main.py \
  --config config.json \
  --bbox -69.9 -6.7 -69.5 -6.3 \
  --date-t0 2024-01-01 \
  --date-t1 2024-06-01 \
  --output outputs/alertas.geojson

   🔬 Metodologia
Pipeline de Processamento
1. Aquisição de Dados (STAC API + Sentinel-2)
   ↓
2. Pré-processamento (Máscara de nuvens)
   ↓
3. Cálculo de Índices (NDVI T0 e T1)
   ↓
4. Detecção de Mudanças (ΔNDVI)
   ↓
5. Vetorização (GeoJSON)
   ↓
6. Publicação (Mapa Interativo)

📈 Resultados
Métricas

✅ F1-Score: 0.73 (Meta: 0.70)
⚡ Latência: 36 horas (Meta: < 48h)
🎯 Acurácia: 87%
📉 15% redução em emissões

Áreas Monitoradas

Eirunepé, AM - Amazônia
Brasília, DF - Cerrado
Balsas, MA - MATOPIBA

Guardiã Verde - Universidade São Judas Tadeu
Projeto desenvolvido no curso de Engenharia de Software.

