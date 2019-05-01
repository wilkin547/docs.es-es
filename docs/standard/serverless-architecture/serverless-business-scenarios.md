---
title: Escenarios de negocio de ejemplo y casos de uso de aplicaciones sin servidor
description: Obtenga información sobre sin servidor con un enfoque práctico mediante el acceso a ejemplos que van desde el procesamiento de imágenes para servidores back-end móvil y las canalizaciones ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 177fb1d7f79a0067ab185e520778b593d4b8eaf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017269"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Escenarios y casos de uso empresariales sin servidor

Hay muchos casos de uso y escenarios para las aplicaciones sin servidor. Este capítulo incluye ejemplos que ilustran los distintos escenarios. Los escenarios incluyen vínculos a documentación relacionada y repositorios de código fuente público. Los ejemplos de este capítulo le permiten empezar a trabajar en su propia creación e implementación de soluciones sin servidor.

## <a name="analyze-and-archive-images"></a>Analizar y archivar las imágenes

Este ejemplo muestra el código (Azure Functions), los flujos de trabajo (aplicación lógica) y sin servidor eventos (Event Grid). También muestra cómo integrar con otro recurso, en este caso Cognitive Services para el análisis de la imagen.

Una aplicación de consola permite pasar un vínculo a una dirección URL en la web. La aplicación publica la dirección URL como un mensaje de la cuadrícula de eventos. En paralelo, una aplicación de función sin servidor y una aplicación lógica se suscriben al mensaje. La aplicación de función sin servidor, serializa la imagen en blob storage. También almacena información en Azure Table Storage. Los metadatos almacenan la dirección URL de imagen original y el nombre de la imagen de blob. La aplicación lógica se interactúa con la API de visión personalizada para analizar la imagen y crear un título generado por la máquina. El título se almacena en la tabla de metadatos.

![Arquitectura de las imágenes de archivo y analizar](./media/image-processing-example.png)

Una aplicación independiente de página única (SPA) llama a una función sin servidor para obtener una lista de imágenes y los metadatos. Para cada imagen, llama a otra función que proporciona los datos de imagen desde el archivo. El resultado final es una galería con automática de subtítulos.

![Galería de imágenes automatizadas](./media/automated-image-gallery.png)

El repositorio completo e instrucciones para crear la aplicación lógica están disponibles aquí: [Pegado de cuadrícula de eventos](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Cliente móvil multiplataforma con Xamarin.Forms y funciones

Vea cómo implementar una sencilla función de Azure sin servidor en el Portal Web de Azure o en Visual Studio. Cree un cliente con Xamarin.Forms que se ejecuta en Windows, iOS y Android. A continuación, se refina de la aplicación para que use JavaScript Object Notation (JSON) como un medio de comunicación entre el servidor y los clientes móviles con un back-end sin servidor.

Para obtener más información, consulte [implementación de una simple función de Azure con un cliente de Xamarin.Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generar un mosaico de foto con reconocimiento de imágenes sin servidor

El ejemplo usa Azure Functions y Microsoft Cognitive Services Custom Vision Service para generar un mosaico de fotografías de una imagen de entrada. El modelo está entrenado para reconocer imágenes. Cuando se carga una imagen, se reconoce la imagen y las búsquedas con Bing. La imagen original se puede volver a componer con los resultados de búsqueda.

![Mosaico y la fotografía de ojo de Orlando](./media/orlando-eye-both.png)

Por ejemplo, puede entrenar el modelo con puntos de referencia de Orlando, por ejemplo, el efecto de ojos Orlando. Custom Vision reconocerá una imagen del ojo Orlando, y la función creará un mosaico de foto formada por los resultados de búsqueda de imágenes de Bing para "Orlando ojos".

Para obtener más información, consulte [generador de mosaic foto de Azure Functions](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migrar una aplicación existente a la nube

Como se describe en los capítulos anteriores, es común a adoptar una arquitectura de N niveles para hospedar su aplicación en modo local. Aunque la migración de recursos "tal cual" uso de máquinas virtuales es la ruta de acceso menos riesgo a la nube, muchas compañías eligen usar la oportunidad para refactorizar sus aplicaciones. Afortunadamente, la refactorización no tiene que ser un esfuerzo "todo o nada". De hecho, es posible migrar la aplicación, a continuación, reemplace por etapas componentes con equivalentes nativos en la nube.

La aplicación utiliza la característica de los servidores proxy de Azure Functions para que la refactorización de un punto de conexión desde el código heredado en el entorno local a un punto de conexión sin servidor.

![Arquitectura de migración](./media/migration-architecture.png)

El proxy proporciona un único punto de conexión de API que se actualiza para enrutar las solicitudes individuales que se mueven a las funciones sin servidor.

Puede ver un vídeo que le guía a través de la migración completa: [Levantar y mover con Azure functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102). Obtener acceso al código de ejemplo: [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analizar un archivo CSV e insertar en una base de datos

Extraer, transformar y carga (ETL) es una función empresarial común que integra sistemas diferentes. Los enfoques tradicionales suelen implican configurar servidores dedicados de FTP, a continuación, implementar los trabajos programados para analizar los archivos y convertirlos para su uso empresarial. Arquitectura sin servidor facilita el trabajo porque se puede activar un desencadenador cuando se cargue el archivo. Tareas de Azure Functions aparejos como ETL a través de su composición ideal de pequeños fragmentos de código que se centran en un problema específico.

![Captura de pantalla que muestra el proceso de análisis de csv.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Para el código fuente y un laboratorio práctico, vea [CSV importar laboratorio](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Acorte los vínculos y realizar un seguimiento de métricas

Herramientas reducir vínculo originalmente ayudado a codificar en resumen de las direcciones URL de twitter publicaciones para acomodar el límite de 140 caracteres. Ha crecido para abarcar varios usos, con más frecuencia para realizar un seguimiento de clics para el análisis. El escenario de shortener vínculo es una aplicación totalmente sin servidor que administra los vínculos y los informes de métricas.

Las funciones de Azure se usa para atender una aplicación de página única (SPA) que le permite pegar la dirección URL larga y generar direcciones URL breves. Las direcciones URL se etiquetan para realizar un seguimiento de las cosas como las campañas (temas) y los medios (por ejemplo, redes sociales que se registran los vínculos). Código corto se almacena en Azure Table Storage como la clave, con la dirección URL larga como el valor. Al hacer clic en el vínculo corto, otra función busca la dirección URL larga, envía una redirección y coloca la información sobre el evento en una cola. Otra función de Azure procesa la cola y coloca la información en Azure Cosmos DB.

![Arquitectura de vínculo shortener](./media/link-shortener-architecture.png)

A continuación, puede crear un panel de Power BI para recopilar información sobre los datos recopilados. En el back-end, Application Insights proporciona métricas importantes. Telemetría incluye cuánto tarda el usuario medio redirigir y cuánto tarda en obtener acceso a Azure Table Storage.

![Ejemplo de Power BI](./media/power-bi-example.png)

El repositorio de shortener vínculo completo con instrucciones está disponible aquí: [Reductor de URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener). Puede leer acerca de una versión simplificada aquí: [Almacenamiento de Azure para aplicaciones .NET sin servidor en cuestión de minutos](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Comprobar la conectividad de dispositivo mediante un ping

El ejemplo consta de un centro de IoT de Azure y una función de Azure. Un mensaje nuevo en el centro de IoT desencadena la función de Azure. El código sin servidor envía el mismo mensaje contenido al dispositivo que lo envió. El proyecto tiene toda la configuración de implementación y el código necesaria para la solución.

Para obtener más información, consulte [ping de Azure IoT Hub](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).

## <a name="recommended-resources"></a>Recursos recomendados

* [Generador de mosaic de Azure Functions foto](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Ping de Azure IoT Hub](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [Almacenamiento de Azure para aplicaciones .NET sin servidor en cuestión de minutos](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [Laboratorio de importación CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Pegado de cuadrícula de eventos](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Implementación de una simple función de Azure con un cliente de Xamarin.Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [Levantar y mover con Azure functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102)
* [Reductor de URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Anterior](orchestration-patterns.md)
>[Siguiente](serverless-conclusion.md)