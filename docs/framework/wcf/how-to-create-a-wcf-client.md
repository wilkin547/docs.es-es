---
title: "Creaci&#243;n de un cliente de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "clientes [WCF], ejecutar"
  - "clientes de WCF [WCF], ejecución"
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: 64
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 64
---
# Creaci&#243;n de un cliente de Windows Communication Foundation
Es la cuarta de las seis tareas necesarias para crear una aplicación de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 En este tema se describe cómo se pueden recuperar metadatos desde un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y usarlos para crear un proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que pueda obtener acceso al servicio.Esta tarea se completa usando la funcionalidad Agregar referencia de servicio proporcionada por Visual Studio.Esta herramienta obtiene los metadatos del extremo MEX del servicio y genera un archivo de código fuente administrado para un proxy de cliente en el lenguaje elegido \(C\# de forma predeterminada\).Además de crear el proxy de cliente, la herramienta también crea o actualiza el archivo de configuración para el cliente que permite que la aplicación cliente se conecte al servicio en uno de sus extremos.  
  
> [!NOTE]
>  También puede usar la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar la clase de proxy y la configuración en lugar de usar Agregar referencia de servicio desde Visual Studio.  
  
> [!WARNING]
>  Cuando se llama a un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] desde un proyecto de biblioteca de clases de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] puede usar la característica Agregar referencia de servicio para generar automáticamente un proxy y el archivo de configuración asociado.El archivo de configuración no lo usará el proyecto de biblioteca de clases.Necesitará agregar los valores del archivo de configuración generado al archivo app.config del ejecutable que llamará a la biblioteca de clases.  
  
 La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio.Este procedimiento se describe en [Cómo utilizar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### Creación de un cliente de Windows Communication Foundation  
  
1.  Cree un nuevo proyecto de aplicación de consola haciendo clic con el botón secundario en la solución Introducción, y seleccionando **Agregar** y **Nuevo proyecto**.En la parte izquierda del cuadro de diálogo **Agregar nuevo proyecto**, seleccione **Ventanas** en **C\#** o **VB**.En la sección central del cuadro de diálogo, seleccione **Aplicación de consola**.Asigne al proyecto el nombre `GettingStartedClient`.  
  
2.  Establezca la versión de .NET Framework de destino del proyecto GettingStartedClient en .NET Framework 4.5 haciendo clic con el botón secundario en **GettingStartedClient** en el Explorador de soluciones y seleccionando **Propiedades**.En el cuadro desplegable **Versión de .NET Framework de destino**, seleccione **.NET Framework 4.5**.Establecer la versión de .NET Framework de destino de un proyecto de VB es algo diferente; en el cuadro de diálogo de propiedades del proyecto GettingStartedClient, haga clic en la pestaña **Compilar** en el lado izquierdo de la pantalla y haga clic en el botón **Opciones de compilación avanzadas** en la esquina izquierda inferior del cuadro de diálogo.Seleccione **.NET Framework 4.5** en el cuadro desplegable **Versión de .NET Framework de destino**.  
  
     Establecer la versión de .NET Framework de destino hará que Visual Studio 2011 recargue la solución; haga clic en **Aceptar** cuando se le pida.  
  
3.  Agregue una referencia a System.ServiceModel al proyecto GettingStartedClient haciendo clic con el botón secundario en la carpeta **Referencia** bajo el proyecto GettingStartedClient en el Explorador de soluciones y seleccione **Agregar referencia**.En el cuadro de diálogo **Agregar referencia**, seleccione **Framework** en el lado izquierdo del cuadro de diálogo.En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`.En la sección central del cuadro de diálogo, seleccione **System.ServiceModel**, haga clic en el botón **Agregar** y haga clic en el botón **Cerrar**.Guarde la solución haciendo clic en el botón **Guardar todo** debajo del menú principal.  
  
4.  Después agregará una referencia de servicio al servicio de Calculadora.Antes de poder hacerlo, debe iniciar la aplicación de consola GettingStartedHost.Una vez que el host está en funcionamiento, puede hacer clic con el botón secundario en la carpeta Referencias bajo el proyecto GettingStartedClient en el Explorador de soluciones y seleccionar Agregar referencia de servicio y escribir la dirección URL siguiente en el cuadro Dirección del cuadro de diálogo Agregar referencia de servicio: http:\/\/localhost:8000\/ServiceModelSamples\/Service y haga clic en el botón **Ir**.CalculatorService se deberá mostrar en el cuadro de lista Servicios; haga doble clic en CalculatorService y se expandirá y mostrará los contratos de servicio implementados por el servicio.Deje el espacio de nombres predeterminado como está y haga clic en el botón **Aceptar**.  
  
     Cuando se agrega una referencia a un servicio usando Visual Studio, aparecerá un nuevo elemento en el Explorador de soluciones bajo la carpeta Referencias de servicio bajo el proyecto GettingStartedClient.Si usa la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), se generará un archivo de código fuente y un archivo app.config.  
  
     También puede usar la herramienta de línea de comandos [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con los modificadores adecuados para crear el código de cliente.El siguiente ejemplo genera un archivo de código y un archivo de configuración para el servicio.El primer ejemplo muestra cómo generar el proxy en VB y el segundo muestra cómo generar el proxy en C\#:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
 Ahora ha creado el proxy que la aplicación cliente usará para llamar al servicio de calculadora.Continúe con el siguiente tema de la serie: [Cómo configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## Vea también  
 [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Introducción:](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Autohospedaje](../../../docs/framework/wcf/samples/self-host.md)   
 [Cómo publicar metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Cómo: Utilizar Svcutil.exe para descargar los documentos de metadatos](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)