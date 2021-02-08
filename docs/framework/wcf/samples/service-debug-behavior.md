---
description: 'Más información sobre: comportamiento de depuración de servicio'
title: Comportamiento de depuración de servicio
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 3aae4a4cca53fce50bff8ec02896e748f430166f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793108"
---
# <a name="service-debug-behavior"></a>Comportamiento de depuración de servicio

Este ejemplo muestra cómo se pueden configurar los valores del comportamiento de servicio de depuración. El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio. Este ejemplo define explícitamente el comportamiento de depuración de servicio en el archivo de configuración. También se puede hacer de forma imperiosa en el código.

En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

El archivo Web.config para el servidor define el comportamiento de depuración del servicio para habilitar como se muestra la página de ayuda y control de excepciones en el ejemplo siguiente.

```xml
<behaviors>
     <serviceBehaviors>
         <behavior name="CalculatorServiceBehavior">
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->
         <!-- Please set this to false when deploying -->
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>
         </behavior>
     </serviceBehaviors>
</behaviors>
```

[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) es el elemento de configuración que permite cambiar las propiedades de comportamiento de depuración del servicio. El usuario puede modificar este comportamiento para lograr lo siguiente:

- Permite al servicio devolver cualquier excepción producida por el código de aplicación aun cuando la excepción no se declare mediante <xref:System.ServiceModel.FaultContractAttribute>. Se ha hecho configurando `includeExceptionDetailInFaults` como `true`. Este valor es útil al depurar los casos donde el servidor produce una excepción inesperada.

  > [!IMPORTANT]
  > No es seguro para activar este valor en un entorno de producción. Una excepción de servidor inesperada puede tener alguna información que no se piensa para el cliente y establecer así `includeExceptionDetailsInFaults` como `true` podría producir pérdida de la información.

- [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)También permite al usuario habilitar o deshabilitar la página de ayuda. Cada servicio puede exponer opcionalmente una página de ayuda que contiene información sobre el servicio que incluye el extremo para obtener WSDL para el servicio. Esto puede estar habilitado estableciendo `httpHelpPageEnabled` como `true`. Esto permite devolver la página de ayuda a una solicitud GET en la dirección base del servicio. Puede cambiar esta dirección estableciendo otro atributo `httpHelpPageUrl`. Puede realizarlo de manera segura utilizando HTTPS en lugar de HTTP. Esto se puede hacer estableciendo `httpsHelpPageEnabled` y `httpsHelpPageUrl`.

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Las primeras tres operaciones (Sumar, Restar y Multiplicar) deben ejecutarse exitosamente. Los últimos errores de la operación ("dividir") con una excepción de división entre cero.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`
