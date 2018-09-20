---
title: Creación de un cliente de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 1eadb5008575a1a53d685db14d68e42d0dce1360
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46478297"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Creación de un cliente de Windows Communication Foundation

Se trata de la cuarta de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).

Este tema describe cómo recuperar los metadatos de un servicio WCF y usarla para crear a un proxy WCF que puede tener acceso al servicio. Esta tarea se completa mediante el uso de la **Add Service Reference** funcionalidad proporcionada por Visual Studio. Esta herramienta obtiene los metadatos del punto de conexión MEX del servicio y genera un archivo de código fuente administrado para un proxy de cliente en el lenguaje elegido (C# de forma predeterminada). Además de crear el proxy de cliente, la herramienta también crea o actualiza el archivo de configuración de cliente que permite que la aplicación cliente se conecte al servicio en uno de sus puntos de conexión.

> [!NOTE]
> También puede usar el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta para generar la clase de proxy y la configuración en lugar de usar **Add Service Reference** en Visual Studio.

> [!NOTE]
> Al llamar a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, puede usar el **Add Service Reference** característica para generar automáticamente un proxy y el archivo de configuración asociada. El archivo de configuración no lo usará el proyecto de biblioteca de clases. Deberá agregar la configuración del archivo de configuración generado para el archivo app.config para el archivo ejecutable que llama a la biblioteca de clases.

La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio. Este procedimiento se describe en [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>Creación de un cliente de Windows Communication Foundation

1. Crear un nuevo proyecto de aplicación de consola en Visual Studio. Haga doble clic en la solución introducción en **el Explorador de soluciones** y seleccione **agregar** > **nuevo proyecto**. En el **Agregar nuevo proyecto** cuadro de diálogo, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#** o **Visual Basic**. Seleccione el **aplicación de consola (.NET Framework)** plantilla y, a continuación, denomine el proyecto **GettingStartedClient**.

2. Agregue una referencia a System.ServiceModel al proyecto GettingStartedClient. Haga doble clic en el **referencias** carpeta bajo el proyecto GettingStartedClient en **el Explorador de soluciones**y, a continuación, seleccione **Agregar referencia**. En el **Agregar referencia** cuadro de diálogo, seleccione **Framework** en el lado izquierdo del cuadro de diálogo **ensamblados**. Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**. Guarde la solución seleccionando **archivo** > **guardar todo**.

3. Agregue una referencia de servicio al servicio de calculadora.

   1. En primer lugar, inicie la aplicación de consola GettingStartedHost.

   2. Una vez que se está ejecutando el host, haga clic en el **referencias** carpeta bajo el proyecto GettingStartedClient en **el Explorador de soluciones** y seleccione **agregar**  >   **Referencia de servicio**.

   3. Escriba la dirección URL siguiente en el cuadro Dirección de la **Add Service Reference** cuadro de diálogo: [http://localhost:8000/GettingStartedClient/Service](http://localhost:8000/GettingStartedClient/Service)

   4. Elija **vaya**.

   CalculatorService se muestra en el **servicios** cuadro de lista. Haga doble clic en CalculatorService para expandirlo y mostrar los contratos de servicio implementados por el servicio. Deje el espacio de nombres predeterminado como-es y elija **Aceptar**.

    Cuando se agrega una referencia a un servicio mediante Visual Studio, aparece un nuevo elemento en **el Explorador de soluciones** bajo el **referencias de servicio** carpeta bajo el proyecto GettingStartedClient. Si usas el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) se generan la herramienta, un archivo de código fuente y el archivo app.config.

    También puede usar la herramienta de línea de comandos [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con los modificadores adecuados para crear el código de cliente. El siguiente ejemplo genera un archivo de código y un archivo de configuración para el servicio. El primer ejemplo muestra cómo generar al proxy en VB, y la segunda muestra cómo generar al proxy en C#:

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

## <a name="next-steps"></a>Pasos siguientes

Ha creado al proxy que usará la aplicación cliente para llamar al servicio de calculadora. Continúe con el siguiente tema de la serie.

> [!div class="nextstepaction"]
> [Cómo configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
- [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Uso de Svcutil.exe para descargar los documentos de metadatos](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
