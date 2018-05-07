---
title: Creación de un cliente de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 962f1255f3c759d623850678005eff138353cc80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Creación de un cliente de Windows Communication Foundation
Se trata de la cuarta de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF). Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.  
  
 En este tema se describe cómo se pueden recuperar metadatos desde un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y usarlos para crear un proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que pueda obtener acceso al servicio. Esta tarea se completa usando la funcionalidad Agregar referencia de servicio proporcionada por Visual Studio. Esta herramienta obtiene los metadatos del extremo MEX del servicio y genera un archivo de código fuente administrado para un proxy de cliente en el lenguaje elegido (C# de forma predeterminada). Además de crear el proxy de cliente, la herramienta también crea o actualiza el archivo de configuración de cliente que permite que la aplicación cliente se conecte al servicio en uno de sus puntos de conexión.  
  
> [!NOTE]
>  También puede usar el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta para generar la clase de proxy y la configuración en lugar de usar Agregar referencia de servicio dentro de Visual Studio.  
  
> [!WARNING]
>  Cuando se llama a un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] desde un proyecto de biblioteca de clases de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] puede usar la característica Agregar referencia de servicio para generar automáticamente un proxy y el archivo de configuración asociado.  El archivo de configuración no lo usará el proyecto de biblioteca de clases. Necesitará agregar los valores del archivo de configuración generado al archivo app.config del ejecutable que llamará a la biblioteca de clases.  
  
 La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio. Este procedimiento se describe en [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>Creación de un cliente de Windows Communication Foundation  
  
1.  Crear un nuevo proyecto de aplicación de consola con el botón secundario en la solución introducción, seleccionar, **agregar**, **nuevo proyecto**. En el **Agregar nuevo proyecto** cuadro de diálogo en el lado izquierdo del cuadro de diálogo, seleccione **Windows** en **C#** o **VB**. En la sección central del cuadro de diálogo Seleccionar **aplicación de consola**. Dé un nombre al proyecto `GettingStartedClient`.  
  
2.  Establezca la plataforma de destino del proyecto GettingStartedClient en .NET Framework 4.5 haciendo clic en **GettingStartedClient** en el Explorador de soluciones y seleccionando **propiedades**. En el cuadro desplegable etiquetado **.NET Framework de destino** seleccione **.NET Framework 4.5**. Establecer la plataforma de destino de un proyecto VB es algo diferente, en el cuadro de diálogo de propiedades de proyecto GettingStartedClient, haga clic en el **compilar** pestaña en el lado izquierdo de la pantalla y, a continuación, haga clic en el **avanzadas Opciones de compilación** situado en la esquina inferior izquierda del cuadro de diálogo. A continuación, seleccione **.NET Framework 4.5** en el cuadro desplegable etiquetado **.NET Framework de destino**.  
  
     Establecer la plataforma de destino hará que Visual Studio 2011 recargue la solución, presione **Aceptar** cuando se le solicite.  
  
3.  Agregue una referencia a System.ServiceModel al proyecto GettingStartedClient haciendo clic en el **referencia** carpeta bajo el proyecto GettingStartedClient en el Explorador de soluciones y seleccione **agregar** Referencia. En el **Agregar referencia** diálogo seleccione **Framework** en el lado izquierdo del cuadro de diálogo. En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`. En la sección central del cuadro de diálogo Seleccionar **System.ServiceModel**, haga clic en el **agregar** y haga clic en el **cerrar** botón. Guarde la solución haciendo clic en el **guardar todo** botón debajo del menú principal.  
  
4.  Después agregará una referencia de servicio al servicio de Calculadora. Antes de poder hacerlo, debe iniciar la aplicación de consola GettingStartedHost. Una vez que se ejecuta el host puede haga clic en la carpeta referencias bajo el proyecto GettingStartedClient en el Explorador de soluciones y seleccione Agregar referencia de servicio y escriba la dirección URL siguiente en el cuadro Dirección del cuadro de diálogo Agregar referencia de servicio: hipervínculo "http://localhost:8000/ServiceModelSamples/Service" http://localhost:8000/ServiceModelSamples/Service y haga clic en el **vaya** botón. CalculatorService se deberá mostrar en el cuadro de lista Servicios; haga doble clic en CalculatorService y se expandirá y mostrará los contratos de servicio implementados por el servicio. Deje el espacio de nombres predeterminado, tal y como está y haga clic en el **Aceptar** botón.  
  
     Cuando se agrega una referencia a un servicio usando Visual Studio, aparecerá un nuevo elemento en el Explorador de soluciones bajo la carpeta Referencias de servicio bajo el proyecto GettingStartedClient.  Si usas el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta generará un archivo de código fuente y el archivo app.config.  
  
     También puede utilizar la herramienta de línea de comandos [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con los modificadores correspondientes para crear el código de cliente. El siguiente ejemplo genera un archivo de código y un archivo de configuración para el servicio. El primer ejemplo muestra cómo generar el proxy en VB y el segundo muestra cómo generar el proxy en C#:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 Ahora ha creado el proxy que la aplicación cliente usará para llamar al servicio de calculadora. Continúe con el siguiente tema de la serie: [Cómo: configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>Vea también  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)  
 [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Uso de Svcutil.exe para descargar los documentos de metadatos](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
