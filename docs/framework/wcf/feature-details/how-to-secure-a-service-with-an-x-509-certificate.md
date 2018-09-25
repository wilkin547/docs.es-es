---
title: 'Cómo: Proteger un servicio con un certificado X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
author: BrucePerlerMS
ms.openlocfilehash: 1c5ab5e76ebed549df09b365a5a271f81003a517
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073559"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a>Cómo: Proteger un servicio con un certificado X.509
Protección de un servicio con un certificado X.509 es una técnica básica que utilizan la mayoría de los enlaces de Windows Communication Foundation (WCF). En este tema se describen los pasos necesarios para configurar un servicio autoalojado con un certificado X.509.  
  
 Un requisito previo es un certificado válido que se puede utilizar para autenticar el servidor. Una entidad emisora de certificados de confianza debe emitir el certificado. Si el certificado no es válido, cualquier cliente que intente usar el servicio no confiará en el servicio y, por tanto, no se realizará ninguna conexión. Para obtener más información sobre el uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a>Configuración de un servicio con un certificado mediante código  
  
1.  Cree el contrato de servicio y el servicio implementado. Para obtener más información, consulte [diseño e implementación de servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
2.  Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3.  Cree dos variables <xref:System.Type>, una para el tipo de contrato y otra para el contrato implementado, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4.  Cree una instancia de la clase <xref:System.Uri> para la dirección base del servicio. Dado que el `WSHttpBinding` utiliza el transporte HTTP, el identificador uniforme de recursos (URI) debe comenzar con ese esquema o Windows Communication Foundation (WCF) se iniciará una excepción cuando se abre el servicio.  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5.  Cree una nueva instancia de la clase <xref:System.ServiceModel.ServiceHost> con la variable del tipo de contrato implementado y el URI.  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6.  Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> al servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Pase el contrato, enlace y una dirección del punto de conexión al constructor, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7.  Opcional. Para recuperar los metadatos del servicio, cree un nuevo objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`.  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8.  Use el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para agregar al servicio el certificado válido. El método puede utilizar un método de varios para encontrar un certificado. Este ejemplo usa la enumeración <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>. La enumeración especifica que el valor proporcionado es el nombre de la entidad a la que se emitió el certificado.  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. Llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> para iniciar la escucha del servicio. Si está creando una aplicación de consola, llame al método <xref:System.Console.ReadLine%2A> para mantener el servicio en el estado de escucha.  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> para configurar un servicio con un certificado X.509.  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los espacios de nombres siguientes son necesarios para compilar el código:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.Web.Services.Description>  
  
-   <xref:System.Security.Cryptography.X509Certificates>  
  
-   <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a>Vea también  
 [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
