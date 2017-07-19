---
title: "Especificaci&#243;n del comportamiento en tiempo de ejecuci&#243;n del servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c5450ea-6af1-4b75-a267-613d0ac54707
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Especificaci&#243;n del comportamiento en tiempo de ejecuci&#243;n del servicio
Una vez que haya diseñado un contrato de servicios \([Diseño de contratos de servicios](../../../docs/framework/wcf/designing-service-contracts.md)\) y haya implementado su contrato de servicios \([Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)\), puede configurar el comportamiento de la operación del tiempo de ejecución del servicio. En este tema se tratan los comportamientos de operaciones y servicios proporcionados por el sistema y se describe dónde encontrar más información para crear nuevos comportamientos. Aunque algunos comportamientos se aplican como atributos, muchos se aplican usando un archivo de configuración de la aplicación o mediante programación.[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo configurar la aplicación de servicio, consulte [Configuración de servicios](../../../docs/framework/wcf/configuring-services.md).  
  
## Información general  
 El contrato define las entradas, las salidas, los tipos de datos y las características de un servicio de ese tipo. Al implementar un contrato de servicios, se crea una clase que, cuando se configura con un enlace en una dirección, cumple el contrato que implementa. El cliente conoce la información contractual, de enlace y dirección; sin esa información, el cliente no puede utilizar el servicio.  
  
 Sin embargo, las características de la operación, como los problemas de los subprocesos o la administración de instancias, son opacas para los clientes. Cuando haya implementado su contrato de servicios, puede configurar un gran número de características de operaciones utilizando los *comportamientos*. Los comportamientos son objetos que modifican el tiempo de ejecución de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] estableciendo una propiedad de tiempo de ejecución o insertando un tipo de personalización en el tiempo de ejecución.[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo modificar el tiempo de ejecución creando comportamientos definidos por el usuario, consulte [Extensión de ServiceHost y la capa de modelos de servicios](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=fullName> y <xref:System.ServiceModel.OperationBehaviorAttribute?displayProperty=fullName> son los comportamientos más útiles y exponen las funciones de operaciones más solicitadas. Puesto que son atributos, se han de aplicar a la implementación de la operación o el servicio. Otros comportamientos, como <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName> o <xref:System.ServiceModel.Description.ServiceDebugBehavior?displayProperty=fullName>, se aplican, normalmente, mediante un archivo de configuración de la aplicación, aunque puede utilizarlos mediante programación.  
  
 Este tema ofrece información general sobre los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>, describe los diversos ámbitos en los que pueden funcionar los comportamientos y proporciona una descripción rápida de muchos de los comportamientos proporcionados por el sistema en los diversos ámbitos que pueden ser de interés para los programadores de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## ServiceBehaviorAttribute y OperationBehaviorAttribute  
 Los comportamientos más importantes son los atributos  <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>, que puede utilizar para controlar:  
  
-   La duración de las instancias  
  
-   La compatibilidad con respecto a la simultaneidad y la sincronización  
  
-   Comportamiento de configuración  
  
-   Comportamiento de transacción  
  
-   Comportamiento de serialización  
  
-   Transformación de metadatos  
  
-   Duración de sesión  
  
-   Filtrado de direcciones y procesamiento de encabezados  
  
-   Suplantación  
  
-   Para utilizar estos atributos, marque el servicio o implementación de la operación con el atributo adecuado a ese ámbito y establezca las propiedades. Por ejemplo, el siguiente ejemplo de código muestra una implementación de la operación que utiliza la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A?displayProperty=fullName> para requerir que los llamadores de esta operación admitan la suplantación.  
  
 [!code-csharp[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/operationbehaviorattribute_impersonation/cs/services.cs#1)]
 [!code-vb[OperationBehaviorAttribute_Impersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationbehaviorattribute_impersonation/vb/services.vb#1)]  
  
 Muchas de las propiedades requieren una compatibilidad adicional del enlace. Por ejemplo, una operación que requiere una transacción del cliente se debe configurar para que utilice un enlace que admita transacciones de flujo.  
  
### Servicios conocidos singleton  
 Puede utilizar los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> para controlar ciertas duraciones, de <xref:System.ServiceModel.InstanceContext> y de los objetos de servicio que implementan las operaciones.  
  
 Por ejemplo, la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName> controla con qué frecuencia se libera el <xref:System.ServiceModel.InstanceContext>, y las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=fullName> y <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=fullName> controlan cuando se libera el objeto de servicios.  
  
 Sin embargo, también puede crear un objeto de servicio y crear el host de servicio mediante ese objeto. Para hacerlo, debe establecer también la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName> en <xref:System.ServiceModel.InstanceContextMode> o se producirá una excepción al abrir el host del servicio.  
  
 Utilice el constructor [ServiceHost.ServiceHost\(Object, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=fullName> para crear este tipo de servicio. Ofrece una alternativa para implementar un <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=fullName> personalizado cuando desee proporcionar una instancia de objeto concreta para su uso con el servicio de singleton. Puede utilizar esta sobrecarga cuando su tipo de implementación de servicio sea difícil de construir \(por ejemplo, si no implementa un constructor público predeterminado que no tiene parámetros\).  
  
 Tenga en cuenta que cuando se proporciona un objeto a este constructor, algunas características relacionadas con el comportamiento de creación de instancias de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] funcionan de manera diferente. Por ejemplo, llamar a <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=fullName>, no tiene ningún efecto cuando se proporciona una instancia de objeto conocida. De igual forma, se omite cualquier otro mecanismo de lanzamiento de instancia. La clase <xref:System.ServiceModel.ServiceHost> siempre se comporta como si la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=fullName> se hubiese establecido en <xref:System.ServiceModel.ReleaseInstanceMode?displayProperty=fullName> para todas las operaciones.  
  
## Otros comportamientos de servicio, extremo, contrato y operación  
 Los comportamientos de servicios, como el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute>, funcionan en a lo largo de todo un servicio. Por ejemplo, si establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=fullName> en <xref:System.ServiceModel.ConcurrencyMode?displayProperty=fullName> debe administrar usted mismo los problemas de sincronización de subprocesos dentro de cada operación de ese servicio. Los comportamientos de extremos funcionan a lo largo de un extremo; muchos de los comportamientos de extremo proporcionados por el sistema se han creado para ofrecer funcionalidad de cliente. Los comportamientos de contratos funcionan en el nivel del contrato y los comportamientos de operaciones modifican la entrega de la operación.  
  
 Muchos de estos comportamientos se implementan en atributos y usted los utiliza como lo haría con los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>; aplicándolos a la clase de servicio o implementación de operaciones adecuada. Otros comportamientos, como los objetos <xref:System.ServiceModel.Description.ServiceMetadataBehavior> o <xref:System.ServiceModel.Description.ServiceDebugBehavior>, se aplican, normalmente, mediante un archivo de configuración de la aplicación, aunque pueden usarse mediante programación.  
  
 Por ejemplo, la publicación de metadatos se configura utilizando el objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. El siguiente archivo de configuración de la aplicación muestra el uso más común.  
  
 [!code-csharp[ServiceMetadataBehavior#1](../../../samples/snippets/csharp/VS_Snippets_CFX/servicemetadatabehavior/cs/hostapplication.cs#1)]  
  
 Las secciones siguientes describen muchos de los comportamientos proporcionados por el sistema más útiles que puede utilizar para modificar la entrega en tiempo de ejecución de su servicio o cliente. Vea el tema de referencia para determinar cómo utilizar cada uno.  
  
### Comportamientos de servicio  
 Los siguientes comportamientos funcionan en servicios.  
  
-   <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>. Aplicado a un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para indicar si ese servicio puede ejecutarse mediante código de compatibilidad de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Controla cómo autoriza el servicio las notificaciones de cliente.  
  
-   <xref:System.ServiceModel.Description.ServiceCredentials>. Configura una credencial de servicio. Utilice esta clase para especificar la credencial del servicio, como un certificado X.509.  
  
-   <xref:System.ServiceModel.Description.ServiceDebugBehavior>. Habilita las características de depuración y de información de Ayuda para un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. Controla la publicación de metadatos de servicio e información asociada.  
  
-   <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>. Especifica el comportamiento de la auditoría de eventos de seguridad.  
  
-   <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>. Configura los valores de rendimiento en tiempo de ejecución que le permiten ajustar el rendimiento del servicio.  
  
### Comportamientos del extremo  
 Los siguientes comportamientos funcionan en extremos. Muchos de estos comportamientos se utilizan en aplicaciones de cliente.  
  
-   <xref:System.ServiceModel.CallbackBehaviorAttribute>. Configura una implementación de servicio de devolución de llamada en una aplicación cliente dúplex.  
  
-   <xref:System.ServiceModel.Description.CallbackDebugBehavior>. Habilita la depuración de servicio para un objeto de devolución de llamada [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   <xref:System.ServiceModel.Description.ClientCredentials>. Permite al usuario configurar las credenciales de cliente y servicio, así como los valores de autenticación de credenciales de servicio para su uso en el cliente.  
  
-   <xref:System.ServiceModel.Description.ClientViaBehavior>. Utilizado por clientes para especificar el Identificador uniforme de recursos \(URI\) para el que se debería crear el canal de transporte.  
  
-   <xref:System.ServiceModel.Description.MustUnderstandBehavior>. Indica a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que deshabilite el procesamiento de `MustUnderstand`.  
  
-   <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>. Indica al tiempo de ejecución que utilice un proceso de recepción sincrónico para los canales.  
  
-   <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Optimiza las operaciones de recepción para los transportes que admiten recepciones transaccionales.  
  
### Comportamientos de contrato  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>. Especifica los requisitos de características que los enlaces deben proporcionar al servicio o implementación del cliente.  
  
### Comportamientos de la operación  
 Los siguientes comportamientos de operación especifican los controles de serialización y transacción de las operaciones.  
  
-   <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. Representa el comportamiento en tiempo de ejecución del <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>.  
  
-   <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>. Controla comportamiento en tiempo de ejecución del `XmlSerializer` y lo asocia a una operación.  
  
-   <xref:System.ServiceModel.TransactionFlowAttribute>. Especifica el nivel en el que una operación de servicio acepta un encabezado de transacción.  
  
## Vea también  
 [Configuración de servicios](../../../docs/framework/wcf/configuring-services.md)   
 [Cómo controlar la creación de instancias de servicio](../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)