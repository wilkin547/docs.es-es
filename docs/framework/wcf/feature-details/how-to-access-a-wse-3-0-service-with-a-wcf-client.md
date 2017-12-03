---
title: "Cómo: Obtener acceso al servicio WSE 3.0 con un cliente WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 787f47f6ca8f25e6df4cc74024febf494f18bf9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Cómo: Obtener acceso al servicio WSE 3.0 con un cliente WCF
Los clientes de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son compatibles en cuanto a conexión con Web Service Enhancements (WSE) para los servicios de Microsoft .NET (3.0) cuando los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se configuran para utilizar la versión de agosto de 2004 de la especificación WS-Addressing. Sin embargo, los servicios de WSE 3.0 no admite el protocolo de intercambio (MEX) de metadatos, por lo que cuando se usa el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clase de cliente, la configuración de seguridad no se aplica a generado [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente. Por consiguiente, debe especificar la configuración de seguridad que el servicio del WSE 3.0 requiere una vez generado el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Puede aplicar esta configuración de seguridad utilizando un enlace personalizado para tener en cuenta los requisitos de servicio de WSE 3.0 y los requisitos interoperables entre un servicio del WSE 3.0 y un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Estos requisitos de interoperabilidad incluyen el uso mencionado anteriormente de agosto de 2004 de la especificación WS-Addressing y la protección predeterminada de mensajes de WSE 3.0 de <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. La protección predeterminada de mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Este tema explica en detalle cómo crear un enlace de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que interopere con un servicio de WSE 3.0. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también proporciona un ejemplo que incorpora este enlace. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]en este ejemplo, vea [interoperar con servicios Web ASMX](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Obtener acceso al servicio Web WSE 3.0 con un cliente WCF  
  
1.  Ejecute el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente para el servicio Web de WSE 3.0.  
  
     Para un servicio Web de WSE 3.0, se crea un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Dado que WSE 3.0 no admite el protocolo MEX, no se puede utilizar la herramienta para recuperar los requisitos de seguridad del Servicio Web. El desarrollador de aplicaciones debe agregar la configuración de seguridad del cliente.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente, consulte la [Cómo: crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Cree una clase que represente un enlace que puede comunicarse con los servicios Web WSE 3.0.  
  
     La siguiente clase forma parte de la [interoperar con WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) ejemplo:  
  
    1.  Cree una clase que se derive de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         En el siguiente ejemplo de código se crea una clase denominada `WseHttpBinding`, que se deriva de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Agregue propiedades a la clase que especifiquen la aserción de llave en mano usada por el servicio WSE, si se requieren las claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes. En WSE 3.0, una aserción de llave en mano especifica los requisitos de seguridad para un cliente o servicio Web, similar al modo de autenticación de un enlace en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
         El ejemplo de código siguiente define las propiedades `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` y `MessageProtectionOrder` que especifican la aserción de llave en mano de WSE, si se requieren claves derivadas, si se usan sesiones seguras, si se requieren confirmaciones de firmas y la configuración de protección de mensajes, respectivamente.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Anule el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> para definir las propiedades de enlace.  
  
         El ejemplo de código siguiente especifica el transporte, codificación de mensajes y configuración de protección de mensajes obteniendo los valores de las propiedades `SecurityAssertion` y `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  En el código de la aplicación cliente, agregue el código para definir las propiedades de enlace.  
  
     El ejemplo de código siguiente especifica que el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe utilizar protección de mensajes y autenticación tal y como define la aserción de seguridad de llave en mano `AnonymousForCertificate` de WSE 3.0. Además, se requieren sesiones seguras y claves derivadas.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente define un enlace personalizado que expone propiedades que corresponden a las propiedades de una aserción de seguridad de llave en mano WSE 3.0. Ese enlace personalizado, que se denomina `WseHttpBinding`, se utiliza a continuación para especificar las propiedades de enlace de un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se comunica con el ejemplo de Tutorial rápido de WSE 3.0 de WSSecurityAnonymous.  
  
  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.Binding>  
 [Interoperar con WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
