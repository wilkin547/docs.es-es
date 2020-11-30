---
title: Especificación del comportamiento en tiempo de ejecución del servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5c5450ea-6af1-4b75-a267-613d0ac54707
ms.openlocfilehash: 61c3b8ebd431c3a16475342984b463d5f8842a89
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2020
ms.locfileid: "96235888"
---
# <a name="specifying-service-run-time-behavior"></a>Especificación del comportamiento en tiempo de ejecución del servicio

Una vez que haya diseñado un contrato de servicios ([Designing Service Contracts](designing-service-contracts.md)) y haya implementado su contrato de servicios ([Implementing Service Contracts](implementing-service-contracts.md)), puede configurar el comportamiento de la operación del tiempo de ejecución del servicio. En este tema se tratan los comportamientos de operaciones y servicios proporcionados por el sistema y se describe dónde encontrar más información para crear nuevos comportamientos. Aunque algunos comportamientos se aplican como atributos, muchos se aplican usando un archivo de configuración de la aplicación o mediante programación. Para obtener más información sobre la configuración de la aplicación de servicio, consulte [configuración de servicios](configuring-services.md).  
  
## <a name="overview"></a>Información general  

 El contrato define las entradas, las salidas, los tipos de datos y las características de un servicio de ese tipo. Al implementar un contrato de servicios, se crea una clase que, cuando se configura con un enlace en una dirección, cumple el contrato que implementa. El cliente conoce la información contractual, de enlace y dirección; sin esa información, el cliente no puede utilizar el servicio.  
  
 Sin embargo, las características de la operación, como los problemas de los subprocesos o la administración de instancias, son opacas para los clientes. Cuando haya implementado su contrato de servicios, puede configurar un gran número de características de operaciones utilizando los *comportamientos*. Los comportamientos son objetos que modifican el tiempo de ejecución de Windows Communication Foundation (WCF) estableciendo una propiedad en tiempo de ejecución o insertando un tipo de personalización en el tiempo de ejecución. Para obtener más información sobre cómo modificar el tiempo de ejecución creando comportamientos definidos por el usuario, consulte [extensión de ServiceHost y la capa de modelo de servicio](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> y <xref:System.ServiceModel.OperationBehaviorAttribute?displayProperty=nameWithType> son los comportamientos más útiles y exponen las funciones de operaciones más solicitadas. Puesto que son atributos, se han de aplicar a la implementación de la operación o el servicio. Otros comportamientos, como <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior?displayProperty=nameWithType>, se aplican, normalmente, mediante un archivo de configuración de la aplicación, aunque puede utilizarlos mediante programación.  
  
 En este tema se proporciona información general sobre los <xref:System.ServiceModel.ServiceBehaviorAttribute> <xref:System.ServiceModel.OperationBehaviorAttribute> atributos y, se describen los diversos ámbitos en los que pueden funcionar los comportamientos y se proporciona una descripción rápida de muchos de los comportamientos proporcionados por el sistema en los diversos ámbitos que pueden ser de interés para los desarrolladores de WCF.  
  
## <a name="servicebehaviorattribute-and-operationbehaviorattribute"></a>ServiceBehaviorAttribute y OperationBehaviorAttribute  

 Los comportamientos más importantes son los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> , que puede utilizar para controlar:  
  
- La duración de las instancias  
  
- La compatibilidad con respecto a la simultaneidad y la sincronización  
  
- Comportamiento de configuración  
  
- Comportamiento de transacción  
  
- Comportamiento de serialización  
  
- Transformación de metadatos  
  
- Duración de sesión  
  
- Filtrado de direcciones y procesamiento de encabezados  
  
- Suplantación  
  
- Para utilizar estos atributos, marque el servicio o implementación de la operación con el atributo adecuado a ese ámbito y establezca las propiedades. Por ejemplo, el siguiente ejemplo de código muestra una implementación de la operación que utiliza la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A?displayProperty=nameWithType> para requerir que los llamadores de esta operación admitan la suplantación.  
  
 [!code-csharp[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/operationbehaviorattribute_impersonation/cs/services.cs#1)]
 [!code-vb[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationbehaviorattribute_impersonation/vb/services.vb#1)]  
  
 Muchas de las propiedades requieren una compatibilidad adicional del enlace. Por ejemplo, una operación que requiere una transacción del cliente se debe configurar para que utilice un enlace que admita transacciones de flujo.  
  
### <a name="well-known-singleton-services"></a>Servicios conocidos singleton  

 Puede utilizar los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> para controlar ciertas duraciones, de <xref:System.ServiceModel.InstanceContext> y de los objetos de servicio que implementan las operaciones.  
  
 Por ejemplo, la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> controla con qué frecuencia se libera el <xref:System.ServiceModel.InstanceContext> , y las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> controlan cuando se libera el objeto de servicios.  
  
 Sin embargo, también puede crear un objeto de servicio y crear el host de servicio mediante ese objeto. Para hacerlo, debe establecer también la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.InstanceContextMode.Single> o se producirá una excepción al abrir el host del servicio.  
  
 Utilice el constructor <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29> para crear este tipo de servicio. Ofrece una alternativa para implementar un <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> personalizado cuando desee proporcionar una instancia de objeto concreta para su uso con el servicio de singleton. Puede usar esta sobrecarga cuando su tipo de implementación de servicio es difícil de construir (por ejemplo, si no implementa un constructor público sin parámetros).
  
 Tenga en cuenta que cuando se proporciona un objeto a este constructor, algunas características relacionadas con el comportamiento de la creación de instancias de Windows Communication Foundation (WCF) funcionan de manera diferente. Por ejemplo, llamar a <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> , no tiene ningún efecto cuando se proporciona una instancia de objeto conocida. De igual forma, se omite cualquier otro mecanismo de lanzamiento de instancia. La clase <xref:System.ServiceModel.ServiceHost> siempre se comporta como si la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> se hubiese establecido en <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> para todas las operaciones.  
  
## <a name="other-service-endpoint-contract-and-operation-behaviors"></a>Otros comportamientos de servicio, extremo, contrato y operación  

 Los comportamientos de servicios, como el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> , funcionan en a lo largo de todo un servicio. Por ejemplo, si establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> debe administrar usted mismo los problemas de sincronización de subprocesos dentro de cada operación de ese servicio. Los comportamientos de extremos funcionan a lo largo de un extremo; muchos de los comportamientos de extremo proporcionados por el sistema se han creado para ofrecer funcionalidad de cliente. Los comportamientos de contratos funcionan en el nivel del contrato y los comportamientos de operaciones modifican la entrega de la operación.  
  
 Muchos de estos comportamientos se implementan en atributos y usted los utiliza como lo haría con los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> ; aplicándolos a la clase de servicio o implementación de operaciones adecuada. Otros comportamientos, como los objetos <xref:System.ServiceModel.Description.ServiceMetadataBehavior> o <xref:System.ServiceModel.Description.ServiceDebugBehavior> , se aplican, normalmente, mediante un archivo de configuración de la aplicación, aunque pueden usarse mediante programación.  
  
 Por ejemplo, la publicación de metadatos se configura utilizando el objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> . El siguiente archivo de configuración de la aplicación muestra el uso más común.  
  
 [!code-xml[ServiceMetadataBehavior#1](../../../samples/snippets/csharp/VS_Snippets_CFX/servicemetadatabehavior/cs/hostapplication.exe.config#1)]  
  
 Las secciones siguientes describen muchos de los comportamientos proporcionados por el sistema más útiles que puede utilizar para modificar la entrega en tiempo de ejecución de su servicio o cliente. Vea el tema de referencia para determinar cómo utilizar cada uno.  
  
### <a name="service-behaviors"></a>Comportamientos de servicio  

 Los siguientes comportamientos funcionan en servicios.  
  
- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>. Se aplica a un servicio WCF para indicar si ese servicio se puede ejecutar en modo de compatibilidad de ASP.NET.  
  
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Controla cómo autoriza el servicio las notificaciones de cliente.  
  
- <xref:System.ServiceModel.Description.ServiceCredentials>. Configura una credencial de servicio. Utilice esta clase para especificar la credencial del servicio, como un certificado X.509.  
  
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>. Habilita las características de depuración y de información de ayuda para un servicio WCF.  
  
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. Controla la publicación de metadatos de servicio e información asociada.  
  
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>. Especifica el comportamiento de la auditoría de eventos de seguridad.  
  
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>. Configura los valores de rendimiento en tiempo de ejecución que le permiten ajustar el rendimiento del servicio.  
  
### <a name="endpoint-behaviors"></a>Comportamientos del extremo  

 Los siguientes comportamientos funcionan en extremos. Muchos de estos comportamientos se utilizan en aplicaciones de cliente.  
  
- <xref:System.ServiceModel.CallbackBehaviorAttribute>. Configura una implementación de servicio de devolución de llamada en una aplicación cliente dúplex.  
  
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>. Habilita la depuración del servicio para un objeto de devolución de llamada de WCF.  
  
- <xref:System.ServiceModel.Description.ClientCredentials>. Permite al usuario configurar las credenciales de cliente y servicio, así como los valores de autenticación de credenciales de servicio para su uso en el cliente.  
  
- <xref:System.ServiceModel.Description.ClientViaBehavior>. Utilizado por clientes para especificar el Identificador uniforme de recursos (URI) para el que se debería crear el canal de transporte.  
  
- <xref:System.ServiceModel.Description.MustUnderstandBehavior>. Indica a WCF que deshabilite el `MustUnderstand` procesamiento.  
  
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>. Indica al tiempo de ejecución que utilice un proceso de recepción sincrónico para los canales.  
  
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Optimiza las operaciones de recepción para los transportes que admiten recepciones transaccionales.  
  
### <a name="contract-behaviors"></a>Comportamientos de contrato  

 <xref:System.ServiceModel.DeliveryRequirementsAttribute>. Especifica los requisitos de características que los enlaces deben proporcionar al servicio o implementación del cliente.  
  
### <a name="operation-behaviors"></a>Comportamientos de la operación  

 Los siguientes comportamientos de operación especifican los controles de serialización y transacción de las operaciones.  
  
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. Representa el comportamiento en tiempo de ejecución del <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>. Controla comportamiento en tiempo de ejecución del `XmlSerializer` y lo asocia a una operación.  
  
- <xref:System.ServiceModel.TransactionFlowAttribute>. Especifica el nivel en el que una operación de servicio acepta un encabezado de transacción.  
  
## <a name="see-also"></a>Consulte también

- [Configuración de servicios](configuring-services.md)
- [Procedimiento para controlar la creación de instancias de servicio](./feature-details/how-to-control-service-instancing.md)
