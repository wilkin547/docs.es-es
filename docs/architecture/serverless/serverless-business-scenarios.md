---
title: Escenarios empresariales de ejemplo y casos de uso de aplicaciones sin servidor
description: Aprenda sin servidor con un enfoque práctico mediante el acceso a ejemplos que van desde el procesamiento de imágenes hasta los back-ends móviles y las canalizaciones ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7024a33f8a7fccd6afa51c126454afedd87cceee
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834296"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Escenarios y casos de uso empresariales sin servidor

Hay muchos casos de uso y escenarios para aplicaciones sin servidor. En este capítulo se incluyen ejemplos que muestran los distintos escenarios. Los escenarios incluyen vínculos a documentación relacionada y repositorios de código fuente públicos. Los ejemplos de este capítulo le permiten empezar a trabajar en su propia creación e implementación de soluciones sin servidor.

## <a name="analyze-and-archive-images"></a>Analizar y archivar imágenes

Este ejemplo muestra eventos sin servidor (Event Grid), flujos de trabajo (aplicación lógica) y código (Azure Functions). También se muestra cómo integrar con otro recurso, en este caso Cognitive Services para el análisis de imágenes.

Una aplicación de consola permite pasar un vínculo a una dirección URL en la Web. La aplicación publica la dirección URL como un mensaje de Event Grid. En paralelo, una aplicación de función sin servidor y una aplicación lógica se suscriben al mensaje. La aplicación de función sin servidor serializa la imagen en el almacenamiento de blobs. También almacena información en Azure Table Storage. Los metadatos almacenan la dirección URL de la imagen original y el nombre de la imagen de BLOB. La aplicación lógica interactúa con el Custom Vision API para analizar la imagen y crear un título generado por el equipo. El título se almacena en la tabla de metadatos.

![Arquitectura de análisis y almacenamiento de imágenes](./media/image-processing-example.png)

Una aplicación de una sola página (SPA) independiente llama a una función sin servidor para obtener una lista de imágenes y metadatos. Para cada imagen, llama a otra función que entrega los datos de imagen del archivo. El resultado final es una galería con subtítulos automáticos.

![Galería de imágenes automatizada](./media/automated-image-gallery.png)

El repositorio completo y las instrucciones para compilar la aplicación lógica están disponibles aquí: [Adherencia de Event Grid](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Cliente móvil multiplataforma con Xamarin. Forms y Functions

Vea cómo implementar una función simple sin servidor de Azure en el portal web de Azure o en Visual Studio. Compilar un cliente con Xamarin. Forms que se ejecuta en Android, iOS y Windows. A continuación, la aplicación se refina para usar notación de objetos JavaScript (JSON) como un medio de comunicación entre el servidor y los clientes móviles con un back-end sin servidor.

Para obtener más información, consulte [implementación de una función de Azure simple con un cliente de Xamarin. Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generación de un mosaico fotográfico con reconocimiento de imágenes sin servidor

En el ejemplo se usa Azure Functions y Microsoft Cognitive Services Custom Vision Service para generar un mosaico fotográfico a partir de una imagen de entrada. El modelo está entrenado para reconocer imágenes. Cuando se carga una imagen, reconoce la imagen y realiza búsquedas con Bing. La imagen original se recompone con los resultados de la búsqueda.

![Foto y mosaico ocular de Orlando](./media/orlando-eye-both.png)

Por ejemplo, puede entrenar el modelo con puntos de referencia de Orlando, como el ojo de Orlando. Custom Vision reconocerá una imagen del ojo de Orlando y la función creará un mosaico fotográfico compuesto por los resultados de la búsqueda de imágenes de Bing para "Orlando Eye".

Para obtener más información, vea [Azure Functions generador de mosaicos fotográficos](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migración de una aplicación existente a la nube

Como se explicó en los capítulos anteriores, es habitual adoptar una arquitectura de N niveles para hospedar su aplicación en el entorno local. Aunque la migración de recursos "tal cual", el uso de máquinas virtuales es la ruta de acceso menos arriesgada a la nube, muchas empresas optan por usar la oportunidad de refactorizar sus aplicaciones. Afortunadamente, la refactorización no tiene que ser un esfuerzo de "todo o nada". De hecho, es posible migrar la aplicación y, a continuación, reemplazar componentes con homólogos nativos en la nube.

La aplicación utiliza la característica de servidores proxy de Azure Functions para permitir la refactorización de un punto de conexión de código local heredado a un punto de conexión sin servidor.

![Arquitectura de migración](./media/migration-architecture.png)

El proxy proporciona un único punto de conexión de API que se actualiza para redistribuir las solicitudes individuales a medida que se mueven a funciones sin servidor.

Puede ver un vídeo que recorre toda la migración: [Eleve y cambie con Azure Functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102). Obtenga acceso al código de ejemplo: [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analizar un archivo CSV e insertarlo en una base de datos

Extraer, transformar y cargar (ETL) es una función empresarial común que integra distintos sistemas. Los enfoques tradicionales suelen implicar la configuración de servidores FTP dedicados y, después, la implementación de trabajos programados para analizar archivos y traducirlos para su uso empresarial. La arquitectura sin servidor facilita el trabajo porque se puede activar un desencadenador cuando se carga el archivo. Azure Functions aborda tareas como ETL a través de su composición ideal de pequeños fragmentos de código que se centran en un problema específico.

![Captura de pantalla que muestra el proceso de análisis de CSV.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Para ver el código fuente y un laboratorio práctico, vea el [laboratorio de importación de CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Acortar vínculos y realizar un seguimiento de las métricas

Las herramientas de reducción de vínculos ayudaron originalmente a codificar direcciones URL en publicaciones cortas de Twitter para acomodar el límite de 140 caracteres. Han crecido para abarcar varios usos, normalmente para hacer un seguimiento de los clics para realizar análisis. El escenario de acortador de vínculos es una aplicación totalmente sin servidor que administra las métricas de vínculos e informes.

Azure Functions se usa para dar servicio a una aplicación de una sola página (SPA) que le permite pegar la dirección URL larga y generar direcciones URL cortas. Las direcciones URL se etiquetan para realizar el seguimiento de elementos como campañas (temas) y medios (como redes sociales a las que se publican los vínculos). El código corto se almacena en Azure Table Storage como la clave, con la dirección URL larga como valor. Al hacer clic en el vínculo corto, otra función busca la dirección URL larga, envía una redirección y coloca información sobre el evento en una cola. Otra función de Azure procesa la cola y coloca la información en Azure Cosmos DB.

![Arquitectura de acortador de vínculos](./media/link-shortener-architecture.png)

Después, puede crear un panel de Power BI para recopilar información sobre los datos recopilados. En el back-end, Application Insights proporciona métricas importantes. La telemetría incluye cuánto tiempo tarda el usuario promedio en redirigirse y cuánto tiempo se tarda en acceder a Azure Table Storage.

![Ejemplo de Power BI](./media/power-bi-example.png)

El repositorio de acortador de vínculos completo con instrucciones está disponible aquí: [Acortador de URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener). Puede leer sobre una versión simplificada aquí: [Azure Storage para aplicaciones .net sin servidor en minutos](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Comprobar la Conectividad del dispositivo mediante un ping

El ejemplo consta de una Azure IoT Hub y una función de Azure. Un nuevo mensaje en el IoT Hub desencadena la función de Azure. El código sin servidor envía el mismo contenido de mensaje de nuevo al dispositivo que lo envió. El proyecto tiene todo el código y la configuración de implementación necesarios para la solución.

Para obtener más información, consulte [Azure IOT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).

## <a name="recommended-resources"></a>Recursos recomendados

* [Azure Functions generador de mosaicos fotográficos](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Azure IoT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [Azure Storage para aplicaciones .NET sin servidor en minutos](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
* [Traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [Laboratorio de importación de CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Adherencia de Event Grid](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Implementación de una función de Azure sencilla con un cliente de Xamarin. Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [Elevación y desplazamiento con Azure Functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102)
* [Acortador de URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Anterior](orchestration-patterns.md)
>[Siguiente](serverless-conclusion.md)
