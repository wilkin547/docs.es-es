---
title: Ejemplos de escenarios empresariales y casos de uso de aplicaciones sin servidor
description: Conozca el modo sin servidor con un enfoque práctico mediante ejemplos que van desde el procesamiento de imágenes hasta los back-ends móviles y las canalizaciones de extracción, transformación y carga de datos (ETL).
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76787890"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Escenarios y casos de uso empresariales sin servidor

Hay muchos casos de uso y escenarios para aplicaciones sin servidor. En este capítulo se incluyen ejemplos que muestran los distintos escenarios. Los escenarios incluyen vínculos a documentación relacionada y repositorios de código fuente públicos. Los ejemplos de este capítulo le permiten empezar a trabajar en su propia creación e implementación de soluciones sin servidor.

## <a name="analyze-and-archive-images"></a>Análisis y archivo de imágenes

Este ejemplo muestra eventos sin servidor (Event Grid), flujos de trabajo (Logic Apps) y código (Azure Functions). También se muestra cómo integrar con otro recurso, en este caso Cognitive Services para el análisis de imágenes.

Una aplicación de consola le permite pasar un vínculo a una dirección URL de la web. La aplicación publica la dirección URL como un mensaje de Event Grid. En paralelo, una aplicación de funciones sin servidor y una aplicación lógica se suscriben al mensaje. La aplicación de funciones sin servidor serializa la imagen en Blob Storage. También almacena información en Azure Table Storage. Los metadatos almacenan la dirección URL de la imagen original y el nombre de la imagen del blob. La aplicación lógica interactúa con Custom Vision API para analizar la imagen y crear un título generado por la máquina. El título se almacena en la tabla de metadatos.

![Análisis y archivo de la arquitectura de imágenes](./media/image-processing-example.png)

Una aplicación de página única (SPA) independiente llama a una función sin servidor para obtener una lista de imágenes y metadatos. Por cada imagen, llama a otra función que ofrece los datos de imagen procedentes del archivo. El resultado final es una galería con títulos automáticos.

![Galería de imágenes automatizadas](./media/automated-image-gallery.png)

El repositorio completo y las instrucciones para compilar la aplicación lógica están disponibles aquí: [Event-Grid-Glue](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Cliente móvil multiplataforma con Xamarin.Forms y Functions

Consulte cómo implementar una instancia sencilla sin servidor de Azure Function en el portal web de Azure o en Visual Studio. Cree un cliente con Xamarin.Forms que se ejecute en Android, iOS y Windows. A continuación, la aplicación se refina para usar la notación de objetos JavaScript (JSON) como medio de comunicación entre el servidor y los clientes móviles con un back-end sin servidor.

Para más información, consulte [Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Implementación de una instancia de Azure Function con un cliente de Xamarin.Forms).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generación de un mosaico fotográfico con reconocimiento de imágenes sin servidor

En el ejemplo se usa Azure Functions y Custom Vision Service de Microsoft Cognitive Services para generar un mosaico fotográfico a partir de una imagen de entrada. El modelo está entrenado para reconocer imágenes. Cuando se carga una imagen, reconoce la imagen y realiza búsquedas con Bing. La imagen original se recompone con los resultados de la búsqueda.

![Foto y mosaico del "Orlando Eye"](./media/orlando-eye-both.png)

Por ejemplo, puede entrenar el modelo con puntos de referencia de Orlando como el Orlando Eye. Custom Vision reconocerá una imagen del Orlando Eye y la función creará un mosaico fotográfico compuesto por los resultados de la búsqueda de imágenes de Bing para "Orlando Eye".

Para más información, consulte el artículo [Azure Functions photo mosaic generator](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic) (Generador de mosaicos fotográficos de Azure Functions).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migración de una aplicación existente a la nube

Como se explicó en los capítulos anteriores, es habitual adoptar una arquitectura de n niveles para hospedar su aplicación en el entorno local. Aunque la migración de recursos "tal cual" mediante máquinas virtuales es el método de acceso menos arriesgado a la nube, muchas empresas optan por usar la oportunidad de refactorizar sus aplicaciones. Afortunadamente, la refactorización no tiene que ser un esfuerzo de "todo o nada". De hecho, es posible migrar la aplicación y, a continuación, reemplazar por etapas los componentes por sus homólogos nativos en la nube.

La aplicación utiliza la característica de servidores proxy de Azure Functions para permitir la refactorización de un punto de conexión desde un código local heredado a un punto de conexión sin servidor.

![Arquitectura de migración](./media/migration-architecture.png)

El proxy proporciona un único punto de conexión de API que se actualiza para redistribuir las solicitudes individuales a medida que se trasladan a funciones sin servidor.

Puede ver un vídeo que recorre todo el proceso de la migración: [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102) (Migración lift-and-shift con instancias de Azure Functions sin servidor). Acceda al código de ejemplo: [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Análisis de un archivo CSV e inserción en una base de datos

La función de extracción, transformación y carga de datos (ETL) es una función empresarial común que integra distintos sistemas. Los enfoques tradicionales suelen implicar la configuración de servidores FTP dedicados y, después, la implementación de trabajos programados para analizar archivos y traducirlos para su uso empresarial. La arquitectura sin servidor facilita el trabajo porque se puede activar un desencadenador cuando se carga el archivo. Azure Functions afronta tareas como la extracción, transformación y carga de datos mediante su composición ideal de pequeños fragmentos de código que se centran en un problema específico.

![Captura de pantalla que muestra el proceso de análisis de un archivo CSV.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Para ver el código fuente y un laboratorio práctico, consulte el [laboratorio de importación de archivos CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Acortamiento de vínculos y seguimiento de métricas

Las herramientas de acortamiento de vínculos ayudaban originalmente a codificar direcciones URL en publicaciones cortas de Twitter para adaptarse al límite de 140 caracteres. Han evolucionado para abarcar varios usos, normalmente para hacer un seguimiento del número de clics con fines de análisis. El escenario del acortador de vínculos es una aplicación completamente sin servidor que administra las métricas de vínculos e informes.

Azure Functions se usa para dar servicio a una aplicación de página única que le permite pegar la dirección URL larga y generar direcciones URL cortas. Las direcciones URL se etiquetan para realizar el seguimiento de elementos como campañas (temas) y medios (como redes sociales en las que se publican los vínculos). El código corto se almacena en Azure Table Storage como clave, con la dirección URL larga como valor. Cuando hace clic en el vínculo corto, otra función busca la dirección URL larga, envía una redirección y coloca la información sobre el evento en una cola. Otra instancia de Azure Functions procesa la cola y coloca la información en Azure Cosmos DB.

![Arquitectura del acortador de vínculos](./media/link-shortener-architecture.png)

Ahora, puede crear un panel de Power BI para recopilar información sobre los datos recopilados. En el back-end, Application Insights proporciona métricas importantes. Los datos de telemetría incluyen cuánto tiempo tarda un usuario medio en completar la redirección y cuánto tiempo se tarda en acceder a Azure Table Storage.

![Ejemplo de Power BI](./media/power-bi-example.png)

El repositorio completo del acortador de vínculos junto con instrucciones está disponible aquí: [Acortador de direcciones URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener). Puede leer sobre una versión simplificada aquí: [Azure Storage for serverless .NET apps in minutes](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/) (Azure Storage para aplicaciones .NET sin servidor en cuestión de minutos).

## <a name="verify-device-connectivity-using-a-ping"></a>Comprobación de la conectividad de dispositivos mediante un ping

El ejemplo consta de una instancia de Azure IoT Hub y de una de Azure Functions. Un nuevo mensaje en IoT Hub desencadena la función de Azure. El código sin servidor envía el mismo contenido de mensaje de nuevo al dispositivo que lo envió. El proyecto tiene todo el código y la configuración de implementación necesarios para la solución.

Para más información, consulte [Ping de Azure IoT Hub](https://github.com/Azure-Samples/iot-hub-node-ping).

## <a name="recommended-resources"></a>Recursos recomendados

- [Azure Functions photo mosaic generator](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic) (Generador de mosaicos fotográficos de Azure Functions)
- [Ping de Azure IoT Hub](https://github.com/Azure-Samples/iot-hub-node-ping)
- [Azure Storage for serverless .NET apps in minutes](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/) (Azure Storage para aplicaciones .NET sin servidor en cuestión de minutos)
- [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [Laboratorio de importación de archivos CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [Event-Grid-Glue](https://github.com/JeremyLikness/Event-Grid-Glue)
- [Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Implementación de una instancia de Azure Function con un cliente de Xamarin.Forms)
- [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102) (Migración lift-and-shift con instancias de Azure Functions sin servidor)
- [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener) (Acortador de direcciones URL sin servidor)

>[!div class="step-by-step"]
>[Anterior](orchestration-patterns.md)
>[Siguiente](serverless-conclusion.md)
