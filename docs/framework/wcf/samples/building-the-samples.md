---
title: Compilación de los ejemplos de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 53599b3b1827651b48df9921bb59a679a36ee39c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592624"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Compilación de los ejemplos de Windows Communication Foundation

Los ejemplos de Windows Communication Foundation (WCF) se pueden compilar con el IDE de Visual Studio o mediante el comando **msbuild** desde la línea de comandos. Ambos procedimientos se describen en este tema.

> [!NOTE]
> Antes de compilar o ejecutar cualquiera de los ejemplos de WCF, asegúrese de que ha realizado el [procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

## <a name="to-build-the-sample-using-a-command-prompt"></a>Para compilar el ejemplo desde un símbolo del sistema

1. Abra Símbolo del sistema para desarrolladores para Visual Studio y navegue hasta el subdirectorio específico del idioma en la ubicación del directorio donde instaló el ejemplo.

2. Escriba `msbuild` en la línea de comandos. Los archivos de programa de cliente se compilan en *client\bin* y los archivos de programa de servicio se compilan en *service\bin*. Si el servicio se hospeda en Internet Information Services (IIS), los archivos de programa de servicio también se copian en el directorio *servicemodelsamples* y en su subdirectorio *\Bin* .

> [!NOTE]
> Debe establecer las ACL en *%systemdrive%\inetpub\wwwroot* para conceder permisos de modificación a la cuenta en la que se ejecuta. De lo contrario, se producirán errores en eventos posteriores a la compilación. Como alternativa, puede dejar las ACL tal como están y ejecutar el símbolo del sistema del SDK como administrador.

## <a name="to-build-the-sample-using-visual-studio"></a>Para compilar el ejemplo con Visual Studio

1. En el menú **archivo** de Visual Studio, seleccione **abrir**  >  **proyecto o solución**. Navegue hasta el subdirectorio específico del lenguaje en el directorio en el que instaló el ejemplo y haga doble clic en el icono del archivo. sln para abrir la solución en Visual Studio.

1. En el menú **compilar** , seleccione **recompilar solución**.

   Los archivos de programa del cliente se compilan en client\bin y los archivos de programa del servicio se compilan en service\bin. Si el servicio se hospeda en IIS, los archivos de programa de servicio también se copian en el directorio *servicemodelsamples* y en su subdirectorio *\Bin* .

> [!NOTE]
> Debe establecer las ACL en %systemdrive%\inetpub\wwwroot para otorgar permisos de modificación en la cuenta bajo la cual se está ejecutando. De lo contrario, se producirán errores en eventos posteriores a la compilación. De manera alternativa, puede dejar las ACL tal y como están y ejecutar el símbolo de sistema de SDK o Visual Studio como administrador. Algunas acciones de Visual Studio (como asociar un depurador al proceso de trabajo de ASP.NET) también requieren privilegios de administrador.

## <a name="setup-batch-files-and-scripts"></a>Archivos de instalación por lotes y scripts
 Los scripts y archivos por lotes de Setup. exe y Cleanup. exe se deben ejecutar desde Símbolo del sistema para desarrolladores para Visual Studio. Hay varios archivos de limpieza e instalación que realizan tareas que requieren privilegios administrativos y deberían iniciarse con privilegios de administrador.

## <a name="important-security-information-about-metadata-endpoints"></a>Información de seguridad importante sobre los puntos de conexión de metadatos
 Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos. Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración. Para que los experimentos con los ejemplos sean más sencillos, casi todos los ejemplos exponen un punto de conexión de publicación de metadatos no seguro. Tales extremos pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que la revelación pública de un metadato del servicio sea la adecuada. Para obtener más información sobre la publicación de metadatos del servicio, vea el ejemplo de [comportamiento de publicación de metadatos](metadata-publishing-behavior.md) . Vea el ejemplo de [extremo de metadatos seguro personalizado](custom-secure-metadata-endpoint.md) para obtener un ejemplo de protección de un extremo de metadatos.

## <a name="exception-handling"></a>Control de excepciones
 En general, estos ejemplos no incluyen el control de excepciones para mantener el código centrado en el asunto del ejemplo. Para obtener más información sobre el control de excepciones, vea el ejemplo de [excepciones esperado](expected-exceptions.md) .

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Regenerar clientes y configuración con Svcutil
 Puede usar la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para regenerar el código de cliente y la configuración de la mayoría de los ejemplos. Algunos ejemplos requieren una configuración editada manualmente. Por ejemplo, si utiliza Svcutil.exe para regenerar la configuración para obtener un ejemplo que utiliza las credenciales del certificado de cliente, debe especificar manualmente las credenciales previamente configuradas. Algunos ejemplos utilizan las opciones Svcutil.exe concretas para afectar al código generado, estas opciones se especifican en los temas de ejemplo concretos.

### <a name="to-regenerate-the-client-and-configuration-files"></a>Para regenerar los archivos de configuración y cliente

1. Abra un símbolo del sistema de SDK y desplácese hasta el subdirectorio específico del idioma debajo de la ubicación del directorio donde haya instalado el ejemplo.

2. Si el servicio es un tipo hospedado en web, utilice el comando siguiente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Si el servicio es un tipo autohospedado utilice el comando siguiente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Reemplace `http://localhost:8000/ServiceModelSamples/service.svc/mex` por la dirección del punto de conexión Mex del servicio autohospedado.

     Para generar el cliente en un tipo de Visual Basic, utilice el siguiente comando.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Si el servicio es un tipo autohospedado utilice el comando siguiente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Para omitir la generación de la configuración del cliente, agregue la opción **/noconfig** .

## <a name="see-also"></a>Vea también

- [Ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
