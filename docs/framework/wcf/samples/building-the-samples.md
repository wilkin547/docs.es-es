---
title: Compilación de los ejemplos de Windows Communication Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcc57d28c109801cc5f995bebd31c49fcbdbe19c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="building-the-windows-communication-foundation-samples"></a>Compilación de los ejemplos de Windows Communication Foundation
El [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ejemplos pueden crearse mediante Visual Studio 2010 o con el **msbuild** comando desde la línea de comandos. Ambos procedimientos se describen en este tema.  
  
> [!NOTE]
>  Antes de compilar o ejecutar cualquiera de los [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ejemplos, asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-build-the-sample-using-a-command-prompt"></a>Para compilar el ejemplo desde un símbolo del sistema  
  
1.  Abra el símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios de administrador y navegue hasta el subdirectorio específico del lenguaje bajo el directorio donde instaló el ejemplo.  
  
2.  Tipo de `msbuild` en la línea de comandos. Los archivos de programa del cliente se compilan en client\bin y los archivos de programa del servicio se compilan en service\bin. Si Internet Information Services (IIS) hospeda el servicio, los archivos de programa del servicio también se copian en el directorio servicemodelsamples y su subdirectorio \bin.  
  
> [!NOTE]
>  Debe establecer las ACL en %systemdrive%\inetpub\wwwroot para otorgar permisos de modificación en la cuenta bajo la cual se está ejecutando. De lo contrario, se producirán errores en eventos posteriores a la compilación. Como alternativa, puede dejar las ACL tal como están y ejecutar el símbolo del sistema del SDK como administrador.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Para compilar el ejemplo con Visual Studio  
  
1.  Si utilizas [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 o Windows Server 2008 R2 y ejecución [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutar Visual Studio con permisos elevados. Para ello, haga clic en el icono en el menú Inicio y, a continuación, haga clic en **ejecutar como administrador**.  
  
2.  Desde el **archivo** menú en Visual Studio, haga clic en **abiertos**, a continuación, haga clic en **proyecto/solución**. Desplácese hasta el subdirectorio específico del lenguaje bajo el directorio en el que instaló el ejemplo y haga doble clic en el icono del archivo .sln para abrir la solución en Visual Studio.  
  
3.  En el **generar** menú, seleccione **volver a generar solución**. Los archivos de programa del cliente se compilan en client\bin y los archivos de programa del servicio se compilan en service\bin. Si se hospeda el servicio en IIS, los archivos de programa de servicio también se copian en el directorio servicemodelsamples y su subdirectorio \bin.  
  
> [!NOTE]
>  Debe establecer las ACL en %systemdrive%\inetpub\wwwroot para otorgar permisos de modificación en la cuenta bajo la cual se está ejecutando. De lo contrario, se producirán errores en eventos posteriores a la compilación. De manera alternativa, puede dejar las ACL tal y como están y ejecutar el símbolo de sistema de SDK o Visual Studio como administrador. Algunas acciones de Visual Studio (como asociar un depurador al proceso de trabajo de ASP.NET) también requieren privilegios de administrador.  
  
## <a name="setup-batch-files-and-scripts"></a>Archivos de instalación por lotes y scripts  
 Los archivos por lotes Setup.exe y Cleanup.exe y los scripts deberían ejecutarse desde un símbolo del sistema de Visual Studio. Hay varios archivos de limpieza e instalación que realizan tareas que requieren privilegios administrativos y deberían iniciarse con privilegios de administrador.  
  
## <a name="important-security-information-about-metadata-endpoints"></a>Información de seguridad importante sobre los puntos de conexión de metadatos  
 Para evitar la divulgación involuntaria de metadatos de servicio con información confidencial potencial, la configuración predeterminada para los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] deshabilita la publicación de metadatos. Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración. Para que los experimentos con los ejemplos sean más sencillos, casi todos los ejemplos exponen un punto de conexión de publicación de metadatos no seguro. Tales puntos de conexión pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales puntos de conexión para garantizar que la revelación pública de un metadato del servicio sea la adecuada. Para obtener más información acerca de la publicación de metadatos de servicio, consulte la [comportamiento de publicación de metadatos](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) ejemplo. Consulte la [personalizado extremo de metadatos seguros](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) ejemplo para obtener un ejemplo de protección de un extremo de metadatos.  
  
## <a name="exception-handling"></a>Control de excepciones  
 En general, estos ejemplos no incluyen el control de excepciones para mantener el código centrado en el asunto del ejemplo. Para obtener más información sobre el control de excepciones, consulte la [espera excepciones](../../../../docs/framework/wcf/samples/expected-exceptions.md) ejemplo.  
  
## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Regenerar clientes y configuración con Svcutil  
 Puede usar el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) volver a generar el código de cliente y la configuración para la mayoría de los ejemplos. Algunos ejemplos requieren una configuración editada manualmente. Por ejemplo, si utiliza Svcutil.exe para regenerar la configuración para obtener un ejemplo que utiliza las credenciales del certificado de cliente, debe especificar manualmente las credenciales previamente configuradas. Algunos ejemplos utilizan las opciones Svcutil.exe concretas para afectar al código generado, estas opciones se especifican en los temas de ejemplo concretos.  
  
#### <a name="to-regenerate-the-client-and-configuration-files"></a>Para regenerar los archivos de configuración y cliente  
  
1.  Abra un símbolo del sistema de SDK y desplácese hasta el subdirectorio específico del idioma debajo de la ubicación del directorio donde haya instalado el ejemplo.  
  
2.  Si el servicio es un tipo hospedado en web, utilice el comando siguiente.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Si el servicio es un tipo autohospedado utilice el comando siguiente.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Reemplace http://localhost:8000/ServiceModelSamples/service.svc/mex con la dirección del extremo mex del servicio hospedado por sí mismo.  
  
     Para generar el cliente en un tipo de Visual Basic, utilice el siguiente comando.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
     Si el servicio es un tipo autohospedado utilice el comando siguiente.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  Para omitir la generación de la configuración de cliente de agregar el **/noConfig** opción.  
  
## <a name="see-also"></a>Vea también  
 [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md)  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
