FreeToGame Browser

Aplicación Flutter que consume la API pública de FreeToGame y muestra una lista de juegos con búsqueda en tiempo real.

Características

Obtiene la lista completa de juegos mediante petición REST GET https://www.freetogame.com/api/games

Modelos Dart robustos que manejan valores nulos y formatos inesperados

Gestión de estado con Provider y ChangeNotifier

Búsqueda en tiempo real mediante TextField y filtro dinámico

Indicador de carga (CircularProgressIndicator) mientras se obtienen datos

Manejo de errores y mensajes de fallo de conexión

Diálogo de detalles al seleccionar un juego

Estructura de carpetas

lib/
├─ api_service/            # Lógica de conexión a la API
│   └─ api_service.dart
├─ models/                 # Modelos de datos (GameData)
│   └─ game_data.dart
├─ viewmodels/             # ViewModels para lógica de presentación
│   └─ game_view_model.dart
├─ views/                  # Vistas (pantallas) de la app
│   └─ game_list_view.dart
└─ main.dart               # Punto de entrada de la aplicación

Dependencias

En pubspec.yaml:

dependencies:
  flutter:
    sdk: flutter
  http: ^0.14.0        # Peticiones HTTP
  provider: ^6.0.5     # Gestión de estado

dev_dependencies:
  flutter_test:
    sdk: flutter

Ejecuta:

flutter pub get

Configuración rápida

Clona el repositorio:

git clone <URL_DEL_PROYECTO>
cd <PROYECTO>

Obtén dependencias:

flutter pub get

Ejecuta en un dispositivo o emulador conectado:

flutter run

Icono de la aplicación

Para definir el icono de la aplicación:

Coloca tu imagen PNG (idealmente cuadrada, 512×512) en assets/icon/app_icon.png.

Añade la configuración en pubspec.yaml:

dev_dependencies:
  flutter_launcher_icons: ^0.14.3

flutter_icons:
  android: true
  ios: false
  image_path: "assets/icon/app_icon.png"

Ejecuta:

flutter pub get
dart run flutter_launcher_icons

Estructura del código clave

``: método fetchGames() que maneja JSON directo o con wrapper { games: [...] }.

``: clase GameData con fromJson tolerante a nulos.

``: lógica de carga, estados (isLoading, errorMessage), filtro dinámico.

``: interfaz con TextField para búsqueda, ListView.builder, y diálogos de detalle.

``: inicializa MaterialApp y arranca con GameListView.