---
description: 'Más información acerca de: varios puntos de conexión en un solo ListenUri'
title: Varios puntos de conexión en un ListenUri único
ms.date: 03/30/2017
ms.assetid: 911ffad4-4d47-4430-b7c2-79192ce6bcbd
ms.openlocfilehash: 20506b05528727a7db2a0720c5c89d237ebd7f5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752226"
---
# <a name="multiple-endpoints-at-a-single-listenuri"></a>Varios puntos de conexión en un ListenUri único

Este ejemplo muestra un servicio que hospeda varios puntos de conexión en un `ListenUri`único. Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Como se muestra en el ejemplo de [varios puntos de conexión](multiple-endpoints.md) , un servicio puede hospedar varios puntos de conexión, cada uno con direcciones diferentes y posiblemente también distintos enlaces. Este ejemplo muestra que es posible hospedar varios extremos en la misma dirección. Este ejemplo también muestra las diferencias entre los dos tipos de direcciones que un extremo de servicio tiene: `EndpointAddress` y `ListenUri`.  
  
 `EndpointAddress` es la dirección lógica de un servicio. Es la dirección a la que se direccionan los mensajes SOAP. `ListenUri` es la dirección física del servicio. Tiene el puerto y direcciona la información hacia donde el punto de conexión del servicio realmente realiza escuchas para los mensajes en el equipo actual. En la mayoría de los casos, no es necesario que estas direcciones difieran; cuando no se especifica `ListenUri` explícitamente, tiene como valor predeterminado el URI de `EndpointAddress` del punto de conexión. En unos casos, es útil para distinguirlos, como al configurar un enrutador, que podría aceptar los mensajes enviado a varios servicios diferentes.  
  
## <a name="service"></a>Servicio  

 El servicio en este ejemplo tiene dos contratos, `ICalculator` e `IEcho`. Además del punto de conexión `IMetadataExchange` de costumbre, hay tres puntos de conexión de la aplicación, tal y como se muestra en el código siguiente.  
  
```xml  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.ICalculator"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:OtherEcho"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
```  
  
 Los tres extremos se hospedan en el mismo `ListenUri` y utilizan el mismo `binding`, los extremos en el mismo `ListenUri` deben tener el mismo enlace, porque están compartiendo una pila de canal única que realiza escuchas para los mensajes en esa dirección física en el equipo. La`address` de cada punto de conexión es un URN; aunque normalmente las direcciones representan las ubicaciones físicas, de hecho la dirección puede ser cualquier tipo de URI, porque la dirección se utiliza para coincidir y filtrar los propósitos como se muestra en este ejemplo.  
  
 Dado que los tres puntos de conexión comparten el mismo `ListenUri` , cuando un mensaje llega allí, Windows Communication Foundation (WCF) debe decidir a qué punto de conexión se destina el mensaje. Cada punto de conexión tiene un filtro de mensajes que se compone de dos partes: el filtro de la dirección y el filtro del contrato. El filtro de la dirección coincide con `To` del mensaje SOAP a la dirección del punto de conexión de servicio. Por ejemplo, solo los mensajes direccionados `To "Urn:OtherEcho"` son candidatos para el tercer punto de conexión de este servicio. El filtro del contrato coincide con las Acciones asociadas a las operaciones de un contrato determinado. Por ejemplo, los mensajes con la acción de `IEcho`. `Echo` coincide con los filtros de contrato del segundo y tercer extremos de este servicio, porque ambos de esos extremos hospedan el contrato `IEcho`.  
  
 Así la combinación de filtro de la dirección y filtro del contrato permite enrutar cada mensaje que llega al`ListenUri` de este servicio al extremo correcto. El tercer punto de conexión se diferencia de los otros dos porque aceptan mensajes enviados a una dirección diferente de los otros puntos de conexión. Los primeros y segundos puntos de conexión se diferencian entre sí basándose en sus contratos (la acción del mensaje entrante).  
  
## <a name="client"></a>Cliente  

 Así como los puntos de conexión en el servidor tienen dos direcciones diferentes, los puntos de conexión del cliente también tienen dos direcciones. En el servidor y el cliente, la dirección lógica se denomina `EndpointAddress`. Pero mientras que la dirección física se denomina `ListenUri` en el servidor, en el cliente, la dirección física se denomina `Via`.  
  
 Como en el servidor, de forma predeterminada, estas dos direcciones son las mismas. Para especificar una`Via` en el cliente que sea diferente de la dirección del extremo, `ClientViaBehavior` se utiliza:  
  
```csharp  
Uri via = new Uri("http://localhost/ServiceModelSamples/service.svc");  
CalculatorClient calcClient = new CalculatorClient();  
calcClient.ChannelFactory.Endpoint.Behaviors.Add(  
        new ClientViaBehavior(via));  
```  
  
 Como de costumbre, la dirección procede del archivo de configuración del cliente, que fue generado por Svcutil.exe. `Via` (Qué corresponde a `ListenUri` del servicio) no aparece en los metadatos del servicio y así esta información se debe comunicar al cliente fuera de banda (simplemente como la dirección de los metadatos del servicio).  
  
 El cliente en este ejemplo envía los mensajes a cada uno de los tres puntos de conexión de la aplicación del servidor, para mostrar que puede comunicarse con (y diferenciar) los tres puntos de conexión, aunque ellos todos tienen el mismo `Via`.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
    > [!NOTE]
    > Para el equipo de cruce, debe reemplazar el localhost en el archivo Client.cs con el nombre del equipo del servicio.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpointsSingleUri`  
