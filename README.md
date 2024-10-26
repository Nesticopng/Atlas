
# Atlas - Wallet Digital 💲

Atlas es una billetera digital que permite realizar operaciones seguras y rápidas. Este README proporciona las instrucciones necesarias para ejecutar el proyecto en un entorno local.


## Requisitos Previos

 - [Node.js](https://nodejs.org/)
 - [MongoDB Account](https://www.mongodb.com/)
 - [PayPal Developer Account](https://developer.paypal.com/)
 - [APILayer Account](https://apilayer.com/)


## Configuración del Entorno

Sigue los pasos a continuación para configurar y ejecutar el proyecto en tu máquina local.

### 1. Clonar el Repositorio

```javascript
git clone https://github.com/Nesticopng/Atlas-Proyecto-Full-Stack
cd atlas-wallet
```

### 2. Instalar Dependencias

Ejecuta el siguiente comando para instalar todas las dependencias del proyecto:

```javascript
npm install
```

### 3. Configuración de Variables de Entorno

1. Crea un archivo `.env` en la carpeta raíz del proyecto 
2. Agrega las siguientes variables de entorno al archivo `.env`:

#### 3.1 Configuración de MongoDB

Para configurar MongoDB Atlas:

* Accede a MongoDB Atlas: MongoDB Atlas e inicia sesión.
* Crea un Proyecto (opcional): Organiza tus clústeres y recursos en un proyecto.
* Crea un Clúster: En la pestaña "Clusters", selecciona "Create a New Cluster". Configura las opciones deseadas y espera a que se cree.
* Configura el Clúster: Ajusta los permisos de acceso y crea un usuario con contraseña para acceder al clúster.
* Obtén el URL de conexión:

    * En la pestaña "Connect", selecciona "Connect Your Application".
    * Copia la cadena de conexión en formato `mongodb+srv://<usuario>:<contraseña>@<cluster-url>/<base-de-datos>?retryWrites=true&w=majority`.
    
En tu archivo `.env`, añade:


```bash
MONGODB_URL=mongodb+srv://<usuario>:<contraseña>@<cluster-url>/<base-de-datos>?retryWrites=true&w=majority
```

#### 3.2 Configuración de PayPal API

Para configurar las credenciales de PayPal:

* __Accede a PayPal Developer__: [PayPal Developer](https://developer.paypal.com/).

* __Crea una Aplicación__: En el "Dashboard", selecciona "Create App" y elige un entorno de desarrollo (sandbox).

* __Obtén las Credenciales__: Copia el `Client ID` y `Secret`.

En tu archivo `.env`, añade:

```javascript
PAYPAL_API_CLIENT=<tu_client_id>
PAYPAL_API_SECRET=<tu_secret>
```

#### 3.3 Configuración de APILayer

Para obtener la API Key de APILayer:

* __Accede a APILayer__: [APILayer](https://apilayer.com/).

* __Selecciona la API__: Copia la `API_KEY` del apartado "Exchange Rates Data API".

En tu archivo `.env`, añade:

```bash
API_KEY=<tu_api_key>
```

#### 3.4 Configuración de node-rsa Keys

Para generar las claves RSA:

1. Instala `node-rsa`:

```bash
API_KEY=<tu_api_key>
```

2. Crea un archivo JavaScript con el siguiente código:

```javascript
const NodeRSA = require('node-rsa');

const key = new NodeRSA({ b: 1024 });
const privateKey = key.exportKey('private').replace(/\n/g, ' ');
const publicKey = key.exportKey('public').replace(/\n/g, ' ');

console.log('PRIVATE_KEY:', privateKey);
console.log('PUBLIC_KEY:', publicKey);
```
3. Ejecuta el archivo para generar las claves:

```bash
node <nombre_del_archivo>
```

4. Copia y pega las claves generadas en el archivo `.env`:

```env
PRIVATE_KEY=<private_key_generada>
PUBLIC_KEY=<public_key_generada>
```

### 4. Iniciar la aplicación.

Ejecuta el siguiente comando para iniciar la aplicación:

```bash
npm run start
```

La aplicación estará disponible en `http://localhost:3000` (o el puerto configurado).
## Enlace a la Aplicación en Producción

Puedes acceder a la versión desplegada de la aplicación en:

### [Atlas Billetera Digital 💲](https://apilayer.com/)

@nestico.png 2024
