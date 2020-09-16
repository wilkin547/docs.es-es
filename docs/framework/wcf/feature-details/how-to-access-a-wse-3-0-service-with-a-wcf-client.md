---
title: 'Cómo: Obtener acceso al servicio WSE 3.0 con un cliente WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 847146c2025612689f0d69cc0c23d2be14018c0f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556842"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Cómo: Obtener acceso al servicio WSE 3.0 con un cliente WCF
Los clientes de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con mejoras de servicios web (WSE) 3,0 para los servicios de Microsoft .NET cuando los clientes de WCF están configurados para usar la versión de agosto de 2004 de la especificación WS-Addressing. Sin embargo, los servicios de WSE 3,0 no son compatibles con el protocolo de intercambio de metadatos (MEX), por lo que cuando se usa la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear una clase de cliente de WCF, la configuración de seguridad no se aplica al cliente WCF generado. Por lo tanto, debe especificar la configuración de seguridad que el servicio WSE 3,0 requiere una vez generado el cliente WCF.  
  
 Puede aplicar esta configuración de seguridad mediante un enlace personalizado para tener en cuenta los requisitos del servicio WSE 3,0 y los requisitos interoperables entre un servicio WSE 3,0 y un cliente de WCF. Estos requisitos de interoperabilidad incluyen el uso mencionado anteriormente de agosto de 2004 de la especificación WS-Addressing y la protección predeterminada de mensajes de WSE 3.0 de <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. La protección predeterminada de mensajes de WCF es <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> . En este tema se detalla cómo crear un enlace de WCF que interopere con un servicio WSE 3,0. WCF también proporciona un ejemplo que incorpora este enlace. Para obtener más información sobre este ejemplo, consulte [interoperar con servicios web asmx](../samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Obtener acceso al servicio Web WSE 3.0 con un cliente WCF  
  
1. Ejecute la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un cliente WCF para el servicio Web WSE 3,0.  
  
     Para un servicio Web de WSE 3,0, se crea un cliente de WCF. Dado que WSE 3.0 no admite el protocolo MEX, no se puede utilizar la herramienta para recuperar los requisitos de seguridad del Servicio Web. El desarrollador de aplicaciones debe agregar la configuración de seguridad del cliente.  
  
     Para obtener más información acerca de la creación de un cliente de WCF, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).  
  
2. Cree una clase que represente un enlace que puede comunicarse con los servicios Web WSE 3.0.  
  
     La clase siguiente forma parte del ejemplo de [interoperabilidad con WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) :  
  
    1. Cree una clase que se derive de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         En el siguiente ejemplo de código se crea una clase denominada `WseHttpBinding`, que se deriva de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Agregue propiedades a la clase que especifiquen la aserción de llave en mano usada por el servicio WSE, si se requieren las claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes. En WSE 3,0, una aserción de llave en mano especifica los requisitos de seguridad para un cliente o un servicio Web, de forma similar al modo de autenticación de un enlace en WCF.  
  
         El ejemplo de código siguiente define las propiedades `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` y `MessageProtectionOrder` que especifican la aserción de llave en mano de WSE, si se requieren claves derivadas, si se usan sesiones seguras, si se requieren confirmaciones de firmas y la configuración de protección de mensajes, respectivamente.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. Anule el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> para definir las propiedades de enlace.  
  
         El ejemplo de código siguiente especifica el transporte, codificación de mensajes y configuración de protección de mensajes obteniendo los valores de las propiedades `SecurityAssertion` y `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. En el código de la aplicación cliente, agregue el código para definir las propiedades de enlace.  
  
     En el ejemplo de código siguiente se especifica que el cliente de WCF debe usar la protección de mensajes y la autenticación tal y como se define en la aserción de seguridad inmediata de WSE 3,0 `AnonymousForCertificate` . Además, se requieren sesiones seguras y claves derivadas.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente define un enlace personalizado que expone propiedades que corresponden a las propiedades de una aserción de seguridad de llave en mano WSE 3.0. Ese enlace personalizado, que se denomina `WseHttpBinding` , se utiliza para especificar las propiedades de enlace de un cliente WCF que se comunica con el ejemplo de inicio rápido WSSECURITYANONYMOUS WSE 3,0.  

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.Binding>
- [Interoperarabilidad con WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
