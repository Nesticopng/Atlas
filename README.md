# Atlas - Wallet Digital 💲

Para iniciar este proyecto localmente en un editor de código se ne requiere seguir los siguientes pasos:

  1 - Ejecutar el comando: npm install

  2 - Crear un archivo ".env" en la carpeta main

  3 - Dentro del archivo ".env" deben ir las siguientes variables de entorno: 

      3.1 - La primera variable de entorno sería el URL de tu servidor de MongoDB. Para obtener el URL de tu clúster de MongoDB, sigue los siguientes pasos:
     
          3.1.1 - Accede a MongoDB Atlas: Ve al sitio web de MongoDB Atlas (https://www.mongodb.com/cloud/atlas) e inicia sesión con tu cuenta.
          
          3.1.2 - Crea un Proyecto (opcional): Si aún no tienes un proyecto en MongoDB Atlas, puedes crear uno para organizar tus clústeres y recursos.
          
          3.1.3 - Crea un Clúster: En la pestaña "Clusters" o "Clústeres", haz clic en el botón "Create a New Cluster" o "Crear un Nuevo Clúster". Selecciona las opciones y configuraciones que desees para tu clúster (tamaño, proveedor en la nube, región, etc.), y luego presiona el botón "Create Cluster" o "Crear Clúster".
          
          3.1.4 - Espera a que se cree el Clúster: El proceso de creación puede llevar unos minutos, dependiendo de las opciones seleccionadas.
          
          3.1.5 - Configura el Clúster: Una vez que el clúster esté creado, puedes configurarlo según tus necesidades. Esto puede incluir la habilitación de características adicionales, la configuración de reglas de acceso, la creación de usuarios y contraseñas, etc.
          
          3.1.6 - Obtén el URL de conexión: Una vez que hayas configurado tu clúster, ve a la pestaña "Clusters" o "Clústeres", haz clic en el clúster que acabas de crear para acceder a su detalle y luego selecciona la pestaña "Connect" o "Conectar".
          
          3.1.7 - Elige una opción de conexión: MongoDB Atlas proporciona varias opciones de conexión. Para la mayoría de las aplicaciones Node.js, la opción más común es "Connect Your Application". Esto generará una cadena de conexión en formato URI que puedes utilizar en tu aplicación para conectarte al clúster.
          
          3.1.8 - Copia el URL de conexión: Copia la cadena de conexión que se muestra en la sección "Connect Your Application". Debe tener el siguiente formato o similar:  mongodb+srv://<usuario>:<contraseña>@<cluster-url>/<base-de-datos>?retryWrites=true&w=majority
          
          3.1.9 - Usa el URL de conexión en tu aplicación: Pega el URL de conexión en tu archivo .env en una variable de entorno llamada "MONGODB_URL". Asegúrate de reemplazar <usuario>, <contraseña>, con las credenciales de tu base de datos.
  
      3.2 - La segunda y tercera variable de entorno serían los API Credentials de tu PayPal Developer. Para crear y obtener las API Credentials de tu cuenta de PayPal Developer, sigue estos pasos:
    
          3.2.1 - Regístrate o inicia sesión: Si aún no tienes una cuenta en PayPal Developer, ve al sitio web de PayPal Developer (https://developer.paypal.com) y regístrate. Si ya tienes una cuenta, inicia sesión con tus credenciales.
    
          3.2.2 - Una vez que hayas iniciado sesión, dirígete a la sección "Dashboard" o "Tablero" y haz clic en "Create App" o "Crear Aplicación". Asigna un nombre descriptivo para tu aplicación y selecciona el entorno de desarrollo (sandbox) en el que deseas trabajar.
    
          3.2.3 - Después de crear la aplicación, serás redirigido a la página de configuración de la aplicación. Aquí encontrarás las siguientes credenciales:
    
        Client ID: Es un identificador único para tu aplicación. Será necesario para autenticar tus solicitudes API hacia PayPal.
        
        Secret: Es una clave secreta que se utilizará junto con el Client ID para autenticar tus solicitudes API. Mantén esta información en secreto y no la compartas públicamente.
            
          3.2.4 - La key del "Client ID" la copiaremos y pegaremos en el .env en una variable de entorno llamada PAYPAL_API_CLIENT
    
          3.2.5 - La key del "Secret" la copiaremos y pegaremos en el .env en una variable de entorno llamada PAYPAL_API_SECRET
    
        3.3 - La cuarta variable de entorno sería la key de APILayer. Para obtener la key sigue estos pasos:
    
          3.3.1 - Regístrate o inicia sesión: Si aún no tienes una cuenta en APILayer, ve al sitio web de APILayer (https://apilayer.com/) y regístrate. Si ya tienes una cuenta, inicia sesión.
    
          3.3.2 - Ve al apartado de Exchange Rates Data API y copia el API KEY, esta key la copiaremos y pegaremos en el .env en una variable de entorno llamada API_KEY
  
      3.4 - La quinta y sexta variable de entorno son las keys del node-rsa

          3.4.1 - Para generar las keys del node-rsa en un archivo de Javascript con node vas a instalar la siguiente dependencia con este comando "npm install node-rsa"

          3.4.2 - En este de archivo de Javascript vas a pegar el siguiente código:

const NodeRSA = require('node-rsa');

const key = new NodeRSA({ b: 1024 });

const privateKey = key.exportKey('private').replace(/\n/g, ' ');
const publicKey = key.exportKey('public').replace(/\n/g, ' ');

console.log(privateKey);
console.log(publicKey);

          3.4.3 - Ya una vez ejecutado este código nos generará las 2 keys, la privateKey la pegaremos en nuestro archivo ".env" en una varible de entorno llamada PRIVATE_KEY 

          3.4.4 - La publicKey la pegaremos en una varible de entorno llamada PUBLIC_KEY

  4 - Ejecutamos el comando: npm run start


Si quieres ver esta aplicación ya desplegada en un servicio hosting ingresa al siguiente link:

https://atlas-fgav.onrender.com



@nestico.png - 2023 
