---
title: BasicBinding con seguridad de transporte
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
ms.openlocfilehash: 822a7dcb20c6559a70ba77719b6e7a62633bb31c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575672"
---
# <a name="basicbinding-with-transport-security"></a>BasicBinding con seguridad de transporte

El ejemplo muestra el uso de seguridad de transporte de SSL con el enlace básico. Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`

## <a name="sample-details"></a>Detalles del ejemplo

De forma predeterminada, el enlace básico soporta la comunicación HTTP. El ejemplo muestra cómo habilitar la seguridad de transporte para el enlace básico. Antes de ejecutar el ejemplo, se debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

El código del programa en el ejemplo es idéntico al del servicio [Introducción](getting-started-sample.md) . La definición de extremo y la definición de enlace en los valores de archivo de configuración se han modificado para habilitar la comunicación segura, como se muestra en la configuración del ejemplo siguiente.

```xml
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
   </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"/>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```

Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert. exe, aparecerá una alerta de seguridad al intentar obtener acceso a una dirección HTTPS: en el explorador, como `https://localhost/servicemodelsamples/service.svc` . Para permitir que el cliente de Windows Communication Foundation (WCF) funcione con un certificado de prueba, se agrega código adicional al cliente para suprimir la alerta de seguridad. Este código y la clase acompañante, no es necesario al utilizar los certificados reales.

```csharp
// This code is required only for test certificates such as those
// created by Makecert.exe.
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Instale ASP.NET 4,0 con el siguiente comando:

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

3. Asegúrese de que ha realizado las [instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).

4. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

5. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).
