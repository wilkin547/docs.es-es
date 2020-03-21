---
title: Sesiones, creación de instancias y simultaneidad
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: a7466d819e15f3bfe8def2d9407dcf2c6e0c7346
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184443"
---
# <a name="sessions-instancing-and-concurrency"></a>Sesiones, creación de instancias y simultaneidad
Una *sesión* es una correlación de todos los mensajes enviados entre dos extremos. *Creación de instancias* hace referencia al control de la vida de los objetos de servicio definidos por el usuario y sus objetos <xref:System.ServiceModel.InstanceContext> relacionados. La*simultaneidad* es el término dado al control del número de subprocesos que se ejecutan al mismo tiempo en un <xref:System.ServiceModel.InstanceContext> .  
  
 En este tema se describen estos valores, cómo utilizarlos y las diversas interacciones entre ellos.  
  
## <a name="sessions"></a>Sesiones  
 Cuando un contrato de servicios establece la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, ese contrato está diciendo que todas las llamadas (es decir, los intercambios de mensajes subyacentes que admiten las llamadas) deben formar parte de la misma conversación. Si un contrato especifica que permite sesiones pero no requiere una, los clientes pueden conectarse y establecer o no una sesión. Si la sesión finaliza y se envía un mensaje se envía sobre el mismo canal basado en sesión, se produce una excepción.  
  
 Las sesiones WCF tienen las siguientes características conceptuales principales:  
  
- La aplicación que realiza la llamada inicia y finaliza explícitamente las sesiones.  
  
- Los mensajes entregados durante una sesión se procesan en el orden de recepción.  
  
- Las sesiones correlacionan un grupo de mensajes en una conversación. El significado de esa correlación es una abstracción. Por ejemplo, un canal basado en sesión puede correlacionar mensajes basados en una conexión de red compartida, mientras que otro canal basado en sesión puede correlacionar mensajes basados en una etiqueta compartida en el cuerpo del mensaje. Las características que se pueden derivar a partir de la sesión dependen de la naturaleza de la correlación.  
  
- No hay ningún almacén de datos general asociado a una sesión WCF.  
  
 Si está familiarizado <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> con la clase en ASP.NET aplicaciones y la funcionalidad que proporciona, es posible que observe las siguientes diferencias entre ese tipo de sesión y sesiones WCF:  
  
- ASP.NET sesiones siempre se inician en el servidor.  
  
- ASP.NET sesiones están implícitamente desordenadas.  
  
- ASP.NET sesiones proporcionan un mecanismo general de almacenamiento de datos en todas las solicitudes.  
  
 Las aplicaciones de cliente y servicio interactúan con sesiones de maneras diferentes. Las aplicaciones cliente inician sesiones y, a continuación, reciben y procesan los mensajes enviados dentro de la sesión. Las aplicaciones de servicio pueden utilizar sesiones como un punto de la extensibilidad para agregar comportamiento adicional. Esto se realiza trabajando directamente con <xref:System.ServiceModel.InstanceContext> o implementando un proveedor de contexto de instancia personalizado.  
  
## <a name="instancing"></a>Creación de instancias  
 El comportamiento de la creación de instancias (establecido mediante el uso de la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> ) controla cómo <xref:System.ServiceModel.InstanceContext> se crea en respuesta a los mensajes entrantes. De forma predeterminada, <xref:System.ServiceModel.InstanceContext> está asociado a un objeto de servicio definido por el usuario, estableciendo así (en el caso predeterminado) la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> , también se controla la creación de instancias de objetos de servicio definidos por el usuario. La enumeración <xref:System.ServiceModel.InstanceContextMode> define los modos de creación de instancias.  
  
 Los siguientes modos de creación de instancias están disponibles:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: Un nuevo <xref:System.ServiceModel.InstanceContext> (y, por consiguiente, objeto de servicio) se crea para cada solicitud de cliente.  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: Un nuevo <xref:System.ServiceModel.InstanceContext> (y, por consiguiente, objeto de servicio) se crea para cada nueva sesión del cliente y se mantiene durante el tiempo que dure esa sesión (esto requiere un enlace que admita sesiones).  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: Un <xref:System.ServiceModel.InstanceContext> único (y, por consiguiente, objeto de servicio) administra todas las solicitudes de cliente durante la vida de la aplicación.  
  
 El ejemplo de código siguiente muestra el valor predeterminado de <xref:System.ServiceModel.InstanceContextMode> , <xref:System.ServiceModel.InstanceContextMode.PerSession> que se establecen de manera explícita en una clase de servicio.  
  
```csharp  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorInstance
{
    ...  
}  
```  
  
 Y mientras la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> controla la frecuencia con la que se publica el <xref:System.ServiceModel.InstanceContext> , las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> controlan cuando se publica el objeto de servicio.  
  
### <a name="well-known-singleton-services"></a>Servicios conocidos singleton  
 Una variación en objetos de servicio de instancia únicos es útil a veces: puede crear un objeto de servicio y crear el host del servicio mediante ese objeto. Para hacerlo, debe establecer también la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.InstanceContextMode.Single> o se producirá una excepción al abrir el host del servicio.  
  
 Utilice el constructor <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> para crear este tipo de servicio. Ofrece una alternativa para implementar un <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> personalizado cuando desee proporcionar una instancia de objeto concreta para su uso con el servicio de singleton. Puede usar esta sobrecarga cuando el tipo de implementación de servicio es difícil de construir (por ejemplo, si no implementa un constructor público sin parámetros).  
  
 Tenga en cuenta que cuando se proporciona un objeto a este constructor, algunas características relacionadas con el comportamiento de creación de instancias de Windows Communication Foundation (WCF) funcionan de forma diferente. Por ejemplo, llamar a <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> , no tiene ningún efecto cuando se proporciona una instancia de objeto singleton. De igual forma, se omite cualquier otro mecanismo de publicación de instancia. <xref:System.ServiceModel.ServiceHost> siempre se comporta como si la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> estuviera definida en <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> para todas las operaciones.  
  
### <a name="sharing-instancecontext-objects"></a>Uso compartido de objetos InstanceContext  
 También puede controlar que canal con sesión o llamada se asocia a qué objeto <xref:System.ServiceModel.InstanceContext> realizando esa asociación usted mismo.  
  
## <a name="concurrency"></a>Simultaneidad  
 La simultaneidad es el control del número de subprocesos activos en <xref:System.ServiceModel.InstanceContext> en cualquier un momento. Esto se controla utilizando <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> con la enumeración <xref:System.ServiceModel.ConcurrencyMode> .  
  
 Los tres modos de simultaneidad siguientes están disponibles:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: cada contexto de instancia puede tener a la vez un máximo de un subproceso procesando mensajes en el contexto de la instancia. El resto de subprocesos que deseen utilizar el mismo contexto de instancia se deben bloquear hasta que el subproceso original salga del contexto de la instancia.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: cada instancia de servicio puede tener varios subprocesos procesando mensajes al mismo tiempo. La implementación del servicio debe ser segura para los subprocesos para utilizar este modo de simultaneidad.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: cada instancia de servicio procesa a la vez un mensaje, pero acepta llamadas de operación reentrantes. El servicio solo acepta estas llamadas cuando llama a través de un objeto de cliente WCF.  
  
> [!NOTE]
> Entender y desarrollar código que use de manera segura más de un subproceso puede ser difícil de escribir correctamente. Antes de utilizar los valores <xref:System.ServiceModel.ConcurrencyMode.Multiple> o <xref:System.ServiceModel.ConcurrencyMode.Reentrant> , asegúrese de que su servicio está diseñado correctamente para estos modos. Para más información, consulte <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 El uso de simultaneidad se relaciona con el modo de creación de instancias. En <xref:System.ServiceModel.InstanceContextMode.PerCall> la creación de instancias, la simultaneidad no <xref:System.ServiceModel.InstanceContext> es relevante, porque cada mensaje es <xref:System.ServiceModel.InstanceContext>procesado por un nuevo y, por lo tanto, nunca más de un subproceso está activo en el archivo .  
  
 El siguiente ejemplo de código demuestra cómo establecer la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> en <xref:System.ServiceModel.ConcurrencyMode.Multiple>.  
  
```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]
public class CalculatorService : ICalculatorConcurrency
{
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Las sesiones interactúan con la configuración de InstanceContext  
 Las sesiones y <xref:System.ServiceModel.InstanceContext> interactúan dependiendo de la combinación del valor de la enumeración <xref:System.ServiceModel.SessionMode> en un contrato y la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> en la implementación del servicio, que controla la asociación entre los canales y los objetos de servicio concretos.  
  
 La tabla siguiente muestra el resultado de un canal entrante que admite o no sesiones dada una combinación de los valores de las propiedades <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> del servicio.  
  
|Valor InstanceContextMode|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|- Comportamiento con canal de <xref:System.ServiceModel.InstanceContext> sesión: Una sesión y para cada llamada.<br />- Comportamiento con canal sin sesión: se produce una excepción.|- Comportamiento con canal de <xref:System.ServiceModel.InstanceContext> sesión: Una sesión y para cada llamada.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: Un para cada llamada.|- Comportamiento con canal con sesión: se produce una excepción.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: Un para cada llamada.|  
|PerSession|- Comportamiento con canal con <xref:System.ServiceModel.InstanceContext> sesión: Una sesión y para cada canal.<br />- Comportamiento con canal sin sesión: se produce una excepción.|- Comportamiento con canal con <xref:System.ServiceModel.InstanceContext> sesión: Una sesión y para cada canal.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: Un para cada llamada.|- Comportamiento con canal con sesión: se produce una excepción.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: Un para cada llamada.|  
|Single|- Comportamiento con canal con sesión: Una sesión y una <xref:System.ServiceModel.InstanceContext> para todas las llamadas.<br />- Comportamiento con canal sin sesión: se produce una excepción.|- Comportamiento con canal con <xref:System.ServiceModel.InstanceContext> sesión: Una sesión y para el singleton creado o especificado por el usuario.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: un para el singleton creado o especificado por el usuario.|- Comportamiento con canal con sesión: se produce una excepción.<br />- Comportamiento con canal <xref:System.ServiceModel.InstanceContext> sin sesión: Un para cada singleton creado o para el singleton especificado por el usuario.|  
  
## <a name="see-also"></a>Consulte también

- [Uso de sesiones](../../../../docs/framework/wcf/using-sessions.md)
- [Cómo crear un servicio que requiere sesiones](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
- [Control de la creación de instancias de servicio](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)
- [Concurrencia](../../../../docs/framework/wcf/samples/concurrency.md)
- [Creación de instancias](../../../../docs/framework/wcf/samples/instancing.md)
- [Sesión](../../../../docs/framework/wcf/samples/session.md)
