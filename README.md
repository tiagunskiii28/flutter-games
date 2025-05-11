# FreeToGame Browser

Aplicación Flutter que consume la API pública de [FreeToGame](https://www.freetogame.com/api/) y muestra una lista de juegos con búsqueda en tiempo real.

---

## Características

* Obtiene la lista completa de juegos mediante petición REST `GET https://www.freetogame.com/api/games`
* Modelos Dart robustos que manejan valores nulos y formatos inesperados
* Gestión de estado con `Provider` y `ChangeNotifier`
* Búsqueda en tiempo real mediante `TextField` y filtro dinámico
* Indicador de carga (`CircularProgressIndicator`) mientras se obtienen datos
* Manejo de errores y mensajes de fallo de conexión
* Diálogo de detalles al seleccionar un juego

---

## Estructura de carpetas

```
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
```

---

## Dependencias

En `pubspec.yaml`:

```yaml
dependencies:
  flutter:
    sdk: flutter
  http: ^0.14.0        # Peticiones HTTP
  provider: ^6.0.5     # Gestión de estado

dev_dependencies:
  flutter_test:
    sdk: flutter
```

Ejecuta:

```bash
flutter pub get
```

---

## Configuración rápida

1. Clona el repositorio:

   ```bash
   git clone <URL_DEL_PROYECTO>
   cd <PROYECTO>
   ```

2. Obtén dependencias:

   ```bash
   flutter pub get
   ```

3. Ejecuta en un dispositivo o emulador conectado:

   ```bash
   flutter run
   ```

---


## Estructura del código clave

* \`\`: método `fetchGames()` que maneja JSON directo o con wrapper `{ games: [...] }`.
* \`\`: clase `GameData` con `fromJson` tolerante a nulos.
* \`\`: lógica de carga, estados (`isLoading`, `errorMessage`), filtro dinámico.
* \`\`: interfaz con `TextField` para búsqueda, `ListView.builder`, y diálogos de detalle.
* \`\`: inicializa `MaterialApp` y arranca con `GameListView`.

