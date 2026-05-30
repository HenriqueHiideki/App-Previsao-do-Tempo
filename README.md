# 🌤️ WeatherApp — Previsão do Tempo

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Google Maps](https://img.shields.io/badge/Google_Maps-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white)
![ZXing](https://img.shields.io/badge/ZXing_QR_Code-000000?style=for-the-badge&logo=qrcode&logoColor=white)

> Aplicativo Android de previsão do tempo com mapa interativo e leitura de QR Code, desenvolvido durante a disciplina de **Programação para Dispositivos Móveis**.

---

## 📱 Funcionalidades

- 🌦️ **Previsão do tempo** — lista de previsões em RecyclerView
- 🗺️ **Mapa interativo** — visualização da cidade consultada via Google Maps
- 📷 **Leitura de QR Code** — troca de cidade de consulta via escaneamento
- 🧭 **Navegação por abas** — TabLayout + ViewPager
- ℹ️ **Tela Sobre** — informações do aplicativo
- ⚡ **Splash Screen** — tela de carregamento inicial

---

## 🏗️ Arquitetura do Projeto

```
WeatherApp/
├── SplashActivity.java          # Tela inicial com delay de 3s
├── MainActivity.java            # Activity principal com tabs e QR Code
├── AboutActivity.java           # Tela de informações
├── ViewPagerAdapter.java        # Adapter para navegação entre fragments
├── WeatherFragment.java         # Fragment de previsão do tempo
├── MapFragment.java             # Fragment com Google Maps
├── ForecastAdapter.java         # Adapter do RecyclerView
├── Forecast.java                # Model de previsão
└── res/
    ├── layout/
    │   ├── activity_splash.xml
    │   ├── activity_main.xml
    │   ├── activity_about.xml
    │   ├── fragment_weather.xml
    │   └── fragment_map.xml
    └── menu/
        └── main_menu.xml
```

---

## 🧩 Componentes Utilizados

| Componente | Descrição |
|---|---|
| `SplashActivity` | Tela de splash com Handler de 3 segundos |
| `TabLayout` | Navegação entre abas (Previsão / Mapa) |
| `ViewPager` | Controle de fragments por deslize |
| `RecyclerView` | Lista de previsões do tempo |
| `MapView` | Mapa interativo com marcador da cidade |
| `FloatingActionButton` | Botão para acionar o scanner de QR Code |
| `IntentIntegrator (ZXing)` | Leitura de QR Code para troca de cidade |

---

## 🛠️ Tecnologias e Dependências

```gradle
dependencies {
    // Material Design
    implementation 'com.google.android.material:material:1.x.x'

    // Google Maps
    implementation 'com.google.android.gms:play-services-maps:18.x.x'

    // ZXing — Leitura de QR Code
    implementation 'com.google.zxing:android-integration:3.3.0'

    // AndroidX
    implementation 'androidx.appcompat:appcompat:1.x.x'
    implementation 'androidx.recyclerview:recyclerview:1.x.x'
}
```

---

## 🗺️ Fluxo de Navegação

```
SplashActivity (3s)
        ↓
MainActivity
    ├── Aba "Previsão" → WeatherFragment → RecyclerView
    ├── Aba "Mapa"     → MapFragment → Google Maps
    ├── Menu "Sobre"   → AboutActivity
    └── FAB (QR Code)  → Scanner ZXing → Atualiza cidade
```

---

## 📷 Como usar o QR Code

1. Toque no botão **FAB** na tela principal
2. Aponte a câmera para um QR Code contendo o nome da cidade
3. O aplicativo lê o conteúdo e atualiza a consulta da API automaticamente

---

## 🚀 Como executar

```bash
# Clone o repositório
git clone https://github.com/henrique-hiideki/weather-app.git

# Abra no Android Studio
# File → Open → selecione a pasta do projeto

# Configure sua chave da API do Google Maps em:
# res/values/google_maps_api.xml

# Execute no emulador ou dispositivo físico
# Run → Run 'app'
```

---

## 📋 Pré-requisitos

- Android Studio Arctic Fox ou superior
- SDK Android 21+ (Android 5.0)
- Chave de API do Google Maps
- Dispositivo ou emulador com câmera (para QR Code)

---

## 📚 Contexto Acadêmico

> Projeto desenvolvido durante a disciplina de **Programação para Dispositivos Móveis**
> Curso: Tecnólogo em Análise e Desenvolvimento de Sistemas
> Instituição: Unipar — Universidade Paranaense

---

## 👨‍💻 Autor

**Henrique Hideki Tanno**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/henriquehideki)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/henrique-hiideki)
