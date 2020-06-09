---
title: WS Http dual
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 4acf2491c242099f6c8b6c9c01dc18e9c99c9934
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589739"
---
# <a name="ws-dual-http"></a>WS Http dual

El ejemplo Http dual muestra cómo configurar el enlace `WSDualHttpBinding`. Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS). El servicio implementa un contrato dúplex. La interfaz `ICalculatorDuplex`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. En este ejemplo, la interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones matemáticas, calculando un resultado en ejecución sobre la sesión. Independientemente, el servicio devuelve los resultados en la interfaz `ICalculatorDuplexCallback`. Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio. El enlace `WSDualHttpBinding` admite la comunicación dúplex.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

Para configurar un punto de conexión de servicio con `WSDualHttpBinding`, especifique el enlace en la configuración del punto de conexión según se muestra.

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Al ejecutar el ejemplo, se ven los mensajes devueltos al cliente en la interfaz de devolución de llamada enviada del servicio. Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones. Presione Entrar para cerrar el cliente.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Instale ASP.NET 4,0 con el siguiente comando.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

    > [!IMPORTANT]
    > Al ejecutar el cliente en una configuración entre equipos, asegúrese de reemplazar localhost en el `address` atributo del elemento [ \<endpoint> \<client> de](../../configure-apps/file-schema/wcf/endpoint-of-client.md) y el `clientBaseAddress` atributo del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento del [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento con el nombre del equipo adecuado, como se muestra a continuación:

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```
