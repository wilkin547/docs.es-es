---
title: Servicios unidireccionales
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], one-way service contracts
- WCF [WCF], one-way service contracts
- service contracts [WCF], defining one-way
ms.assetid: 19053a36-4492-45a3-bfe6-0365ee0205a3
ms.openlocfilehash: c4b69d68c52e9f199348544e5838babc9f4d8c2c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248089"
---
# <a name="one-way-services"></a>Servicios unidireccionales

El comportamiento predeterminado de una operación de servicio es el patrón de solicitud-respuesta. En un patrón de este tipo, el cliente espera el mensaje de respuesta, aun cuando la operación de servicio se representa en código como un método `void`. Con una operación unidireccional, sólo se transmite un mensaje. El receptor no envía un mensaje de respuesta, ni el remitente lo espera.  
  
 Use el patrón de diseño unidireccional:  
  
- Cuando el cliente debe llamar a las operaciones y no está afectado por el resultado de la operación en el nivel de la operación.  
  
- Cuando se usa la clase <xref:System.ServiceModel.NetMsmqBinding> o <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. (Para obtener más información acerca de este escenario, vea [colas en WCF](queues-in-wcf.md)).  
  
 Cuando una operación es unidireccional, no hay ningún mensaje de respuesta para devolver la información de error al cliente. Puede detectar las condiciones de error mediante las características del enlace subyacente, como sesiones de confianza, o diseñando un contrato de servicio dúplex que utiliza dos operaciones unidireccionales; es decir, un contrato unidireccional del cliente al servicio para llamar a la operación de servicio y otro contrato unidireccional entre el servicio y el cliente para que el servicio pueda devolver los errores al cliente utilizando una devolución de llamada que el cliente implementa.  
  
 Para crear un contrato de servicio unidireccional, defina su contrato de servicio, aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación y establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true`, tal y como se muestra en el código muestra siguiente.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 Para obtener un ejemplo completo, vea el ejemplo [unidireccional](../samples/one-way.md) .  
  
## <a name="clients-blocking-with-one-way-operations"></a>Clientes que se bloquean con operaciones unidireccionales  

 Es importante tener en cuentan que, mientras que algunas aplicaciones unidireccionales devuelven en cuanto los datos salientes se escriben en la conexión de red, en varios escenarios, la implementación de un enlace o de un servicio puede hacer que un cliente WCF se bloquee mediante operaciones unidireccionales. En las aplicaciones cliente de WCF, el objeto de cliente de WCF no vuelve hasta que los datos salientes se hayan escrito en la conexión de red. Esto se cumple para todos los patrones de intercambio de mensajes, incluidas las operaciones unidireccionales, lo que significa que cualquier problema que se produzca al escribir los datos en el transporte impide que se devuelva el cliente. Dependiendo del problema, el resultado podría ser una excepción o un retraso en el envío de mensajes al servicio.  
  
 Por ejemplo, si el transporte no puede buscar el punto de conexión, se emite una excepción <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType> sin mucho retraso. Sin embargo, también es posible que el servicio no pueda leer los datos fuera de la conexión por alguna razón, lo que evita que se devuelva la operación de envío de transporte del cliente. En estos casos, si se supera el período <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A?displayProperty=nameWithType> en el enlace de transporte de cliente, se emitirá <xref:System.TimeoutException?displayProperty=nameWithType>, pero no hasta que se haya superado el período de tiempo de espera. También es posible activar tantos mensajes en un servicio que el servicio no pueda procesarlos sobrepasado un cierto punto. En este caso también, el cliente unidireccional se bloquea hasta que el servicio pueda procesar los mensajes o hasta que se produzca una excepción.  
  
 Otra variación es la situación en la que la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> del servicio está establecida en <xref:System.ServiceModel.ConcurrencyMode.Single> y el enlace utiliza sesiones. En este caso, el distribuidor exige la clasificación en los mensajes entrantes (un requisito de sesiones), que evita que los mensajes subsiguientes se lean fuera de la red hasta que el servicio haya procesado el mensaje anterior para esa sesión. De nuevo, el cliente se bloquea, pero si una excepción se produce depende de si el servicio puede procesar los datos de espera antes de la configuración del tiempo de espera en el cliente.  
  
 Puede mitigar algunos de estos problemas insertando un búfer entre el objeto de cliente y la operación de envío de transporte del cliente. Por ejemplo, utilizar las llamadas asincrónicas o una cola de mensajes en memoria puede permitir que el objeto de cliente devuelva rápidamente. Ambos enfoques pueden aumentar la funcionalidad, pero el tamaño del grupo de subprocesos y la cola de mensajes todavía exigen límites.  
  
 En su lugar, se recomienda que examine los distintos controles en el servicio así como en el cliente y después pruebe sus escenarios de aplicación para determinar la mejor configuración en cada lado. Por ejemplo, si el uso de sesiones está bloqueando el procesamiento de mensajes en su servicio, puede establecer la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.InstanceContextMode.PerCall> de manera que una instancia del servicio diferente pueda procesar cada mensaje, y establecer <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> en <xref:System.ServiceModel.ConcurrencyMode.Multiple> para permitir que más de un subproceso envíe los mensajes cada vez. Otro enfoque es aumentar las cuotas de lectura de los enlaces de cliente y servicio.  
  
## <a name="see-also"></a>Vea también

- [Unidireccional](../samples/one-way.md)
