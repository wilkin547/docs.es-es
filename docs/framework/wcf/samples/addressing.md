---
title: Direccionamiento
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 4403ac2bf8e0e5193006f6ec19b24a9bcb00bf35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183976"
---
# <a name="addressing"></a>Direccionamiento
El ejemplo de direccionamiento muestra varios aspectos y características de direcciones del extremo. El ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). En este ejemplo, el servicio es hospedado por sí mismo. El cliente y el servicio son aplicaciones de consola. El servicio define varios puntos de conexión mediante una combinación de direcciones del punto de conexión absolutas y relativas.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El archivo de configuración de servicio especifica una dirección base y cuatro puntos de conexión. La dirección base se especifica utilizando el elemento agregar, bajo el servicio/host/baseAddresses como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 La primera definición de punto de conexión mostrada en el siguiente ejemplo de configuración especifica una dirección relativa, lo cual significa que la dirección del punto de conexión es una combinación de la dirección base y la dirección relativa siguiendo las reglas de composición de identificadores uniformes de recursos (URI).  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 En este caso, la dirección relativa está vacía (""), por lo que la dirección del punto de conexión es igual a la dirección base. La dirección real `http://localhost:8000/servicemodelsamples/service`del punto de conexión es .
  
 La segunda definición de extremo también especifica una dirección relativa, como se muestra en el siguiente ejemplo de configuración.  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 La dirección relativa, "test", se anexa a la dirección base. La dirección real `http://localhost:8000/servicemodelsamples/service/test`del punto de conexión es .
  
 La tercera definición de extremo especifica una dirección absoluta, como se muestra en el siguiente ejemplo de configuración.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 La dirección base no desempeña ningún papel en la dirección. La dirección real `http://localhost:8001/hello/servicemodelsamples`del punto de conexión es .
  
 La cuarta dirección del extremo especifica una dirección absoluta y un TCP de transporte diferente. La dirección base no desempeña ningún papel en la dirección. La dirección real `net.tcp://localhost:9000/servicemodelsamples/service`del punto de conexión es .
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</service>  
```  
  
 El cliente tiene acceso solo a uno de los cuatro puntos de conexión de servicio, pero los cuatro se definen en su archivo de configuración. El cliente selecciona un punto de conexión cuando crea el objeto `CalculatorProxy`. Cambiando el nombre de configuración de `CalculatorEndpoint1` a través de `CalculatorEndpoint4`, puede ejercer cada uno de los extremos.  
  
 Al ejecutar el ejemplo, el servicio enumera la dirección, enlazando el nombre y el nombre del contrato para cada uno de sus puntos de conexión. El punto de conexión de intercambio (MEX) de metadatos simplemente es otro punto de conexión de la perspectiva del ServiceHost que se presenta en la lista.  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 Al ejecutar el cliente, las solicitudes de la operación y las respuestas se muestran en las ventanas de la consola del cliente y del servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
    > [!NOTE]
    > Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
