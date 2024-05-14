# Comparação entre GeoPy, OpenStreetMap, Mapbox e Google Maps

## OpenStreetMap (OSM)
- **Descrição:** Projeto colaborativo de mapeamento aberto e gratuito.
- **Características Principais:**
  - Base de dados geoespaciais editável por qualquer pessoa.
  - Fornece dados brutos, como estradas, trilhas e pontos de interesse.
  - Gratuito para uso em projetos comerciais e não comerciais.
- **Uso Típico:** Alimentar serviços de geolocalização em aplicativos, criar mapas personalizados.

## Mapbox
- **Descrição:** Plataforma de mapeamento com opções de personalização.
- **Características Principais:**
  - Personalização extensiva, incluindo design de mapas e estilos.
  - Suporte para navegação turn-by-turn, atualizações de tráfego em tempo real.
  - SDK disponível para integração em aplicativos móveis e web.
- **Uso Típico:** Aplicativos que exigem mapas altamente personalizados e recursos avançados de navegação.

## Google Maps
- **Descrição:** Serviço de mapeamento amplamente reconhecido.
- **Características Principais:**
  - Mapas detalhados, imagens de satélite e Street View.
  - Funcionalidades como busca local, direções e atualizações de tráfego em tempo real.
  - SDK disponível para integração em aplicativos móveis e web.
- **Uso Típico:** Aplicativos que requerem um serviço de mapeamento reconhecido e funcionalidades avançadas de navegação.

## Comparação de Preços
| Característica        | OpenStreetMap | Mapbox       | Google Maps  |
|-----------------------|---------------|--------------|--------------|
| Estrutura de Preços   | Gratuito      | Pagamento conforme o uso | Pagamento conforme o uso |
| Camada Gratuita       | Uso ilimitado | Até 50,000 visualizações de mapas e geocódigos | Crédito mensal de $200 |
| Mapas Estáticos       | Gratuitos     | Gratuitos para os primeiros 50,000, depois $0,60 - $1,00 por 1.000 solicitações | Gratuitos para dispositivos móveis, depois $2 por 1.000 solicitações |
| Geocodificação        | Gratuita      | Gratuita para os primeiros 100,000, depois $4 - $5 por 1.000 solicitações | $5,00 por 1.000 solicitações (além do crédito mensal) |
| Direções / Roteamento | Gratuitos     | Gratuitos para os primeiros 100,000, depois $1,20 - $2 por 1.000 solicitações | $5,00 por 1.000 solicitações (além do crédito mensal) |
| Informações de Tráfego| Gratuitas     | Incluídas no preço das visualizações de mapas | Preços separados, com base em solicitações |
| Modo 3D               | Gratuito      | Disponível   | Disponível    |

Esta tabela fornece uma visão geral das características e preços de cada serviço de mapeamento, ajudando a escolher o mais adequado para o seu projeto.

## Codigo exemplo de comparação 
***Coordenadas de caso de test***

_Origem: (42.51539172836014, -8.808832763662798)_ 

Pazo A Capitana, Rúa Sabugueiro, Sabugueiro, Os Olmos, Vilariño, Cambados, O Grove, O Salnés, Pontevedra, Galicia, 36630, España


_Destino: (42.46310480657001, -8.74192712354374)_ 

Mosteiro de Armenteira, EP-9406, Cuchín, A Armenteira, Meis, O Salnés, Pontevedra, Galicia, 36192, España


Usando essas coordenadas como ponto de referencia no google, estamos a falar de ***10,3KM***
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihalU7aIPAb9cbMlklYE7TmnuAb3TVWXWIp96MR4k2BgGyTLndNLuUS362om6OvGzdE1vHmAaJf7I7EiuSnT9-co6y8JiCwSmmc=s1600-rw-v1)


Atualmente o mesmo exemplo no sistema esta em ***7,99KM***
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihahi014e5xgX24dJvYW7KvnnlGtf_dFuru1Y682-7Ceqg_36sOPHC3u3yf97er73f2W-_LYVCLSXzZp48-zDGTg0HkzGabLDdg=s1600-rw-v1)


Levando em conta as coordenadas aqui esta uma comparação usando as bibliotecas:
- Google Maps (Nota)
Embora o Google Maps seja uma referência amplamente reconhecida e utilizada, seu custo pode ser proibitivo para muitos projetos devido ao seu modelo de cobrança baseado em solicitações. No entanto, suas funcionalidades e precisão podem servir como ponto de referência para comparação.


- Geopy (em uso atualmente) - 7.999414386907035 Km 
Embora o Geopy ofereça uma abordagem interessante ao calcular distâncias com base em linhas retas, sua limitação reside na falta de consideração pelas condições reais da estrada. Isso pode resultar em estimativas imprecisas em comparação com os métodos de roteamento baseados em mapas. No entanto, pode ser uma escolha viável para casos de uso simples e com requisitos de baixo custo.
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihZDFB5UAmsHlYiLJ2JSrOWe3d7LPr6-alXOEQVqqMXCqYmnOKQhHM-av5EvidpgaZlg5nFXcKLo8DJHC_8J4hQXXh4b6QG7Ob0=s1600-rw-v1)


- OSRM (Gratuito) - 10.1496 Km
O OpenStreetMap, em conjunto com o OSRM, destaca-se como uma opção altamente vantajosa devido à sua gratuidade. O uso de dados de código aberto e a capacidade de calcular rotas com base nas estradas reais garantem uma precisão confiável. É uma escolha sólida para projetos com restrições orçamentárias e que necessitam de resultados precisos.
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihZlTsvXGClvzOgY5IDwT-MwrHvLgT3VrbmwxSiKbVfiD2zFHQ1hY2PFBEDlWMGu8ZL2D93ZUQKI6qEFILPhtNxHA2djPXcXwg=s1600-rw-v1)
[Test Map](https://www.openstreetmap.org/directions?engine=graphhopper_car&route=42.5152%2C-8.8092%3B42.4633%2C-8.7420#map=13/42.4980/-8.7633)


- MapBox (Pago) - 10.160298000000001 km
O Mapbox é uma opção paga, mas seu custo é relativamente baixo em comparação com o Google Maps. Sua flexibilidade, recursos avançados e confiabilidade a longo prazo o tornam uma escolha atraente para projetos que exigem precisão e desempenho consistentes. Para empresas que podem investir um pouco mais em suas soluções de mapeamento, o Mapbox oferece uma alternativa robusta e escalável.
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihbC-2-9jIRtyk-BQ1Tjn6QPyTjpWx5xRDci7mKI1H32FaQaxMKpP75x-4vj2LWKoyXoWD2SmX3Ga-F2wgFpxV7d-xzmEpru9Q=s1600-rw-v1)



**KM de cada biblioteca**
![image](https://lh3.googleusercontent.com/drive-viewer/AKGpihZSRJQ0VVG7OCULFBY_Vj6S3oNYpG5rtmTTVa-RRNRPKtZGnI1HWuFXZL53As4uOTob0tEzXWLqU7dF1BHOuCvB92rQYMSWdA=s1600-rw-v1)


## Recomendações:
Em resumo, para projetos com orçamento limitado e que priorizam a gratuidade, o OpenStreetMap com o OSRM é a melhor opção. Para aqueles que valorizam precisão e consideram investir em uma solução de mapeamento a longo prazo, o Mapbox é altamente recomendado. O Geopy pode servir como uma alternativa econômica, mas sua precisão pode ser comprometida em comparação com as APIs de roteamento baseadas em mapas.
