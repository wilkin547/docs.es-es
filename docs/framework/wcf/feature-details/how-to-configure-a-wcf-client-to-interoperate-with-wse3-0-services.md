---
title: 'Cómo: Configurar un cliente WCF para interoperar con los servicios WSE3.0'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 5cbe982049d1df6e2c714ca0b63de0db7577452e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187314"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>Cómo: Configurar un cliente WCF para interoperar con los servicios WSE3.0
Los clientes de Windows Communication Foundation (WCF) son compatibles con el nivel de conexión con Web Services Enhancements 3.0 para servicios de Microsoft .NET (WSE) cuando los clientes de WCF se configuran para usar la versión de agosto de 2004 de la especificación WS-Addressing.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>Configuración de un cliente WCF para interoperar con un servicio web WSE 3.0  
  
1.  Ejecute el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un cliente WCF para el servicio Web WSE 3.0.  
  
     Para un servicio Web de WSE, se crea una clase de cliente WCF.  
  
     Para obtener más información acerca de cómo crear un cliente de WCF, vea el [Cómo: crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Cree una clase que represente un enlace que puede comunicarse con los servicios Web WSE 3.0.  
  
     La clase siguiente forma parte de la [interoperar con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) ejemplo.  
  
    1.  Cree una clase que se derive de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         En el siguiente ejemplo de código se crea una clase denominada `WseHttpBinding`, que se deriva de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Agregue propiedades a la clase que especifiquen la aserción de llave en mano WSE, si se requieren las claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes.  
  
         En el ejemplo de código siguiente se define `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` propiedades que especifican la aserción de llave en mano WSE, si se requieren claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas y la configuración de protección de mensajes respectivamente.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Anule el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> para definir las propiedades de enlace.  
  
         El ejemplo de código siguiente especifica el transporte, codificación de mensajes y configuración de protección de mensajes obteniendo los valores de las propiedades `SecurityAssertion` y `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  En el código de la aplicación cliente, agregue el código para definir las propiedades de enlace.  
  
     El ejemplo de código siguiente especifica que el cliente de WCF debe usar autenticación y protección de mensajes definidos por el WSE 3.0 `AnonymousForCertificate` aserción de seguridad inmediata. Además, se requieren sesiones seguras y claves derivadas.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente define un enlace personalizado que expone propiedades que corresponden a las propiedades de una aserción de seguridad de llave en mano WSE 3.0. El enlace personalizado, que se denomina `WseHttpBinding`, a continuación, se usa para especificar las propiedades de enlace para un cliente WCF.  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.Binding>  
 [Interoperar con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)