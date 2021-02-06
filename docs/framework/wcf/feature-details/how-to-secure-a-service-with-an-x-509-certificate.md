---
description: 'Más información acerca de cómo: proteger un servicio con un certificado X. 509'
title: Procedimiento para proteger un servicio con un certificado X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 57c8e78777c620fd3078651dbafbbf010fbd3768
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643389"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a><span data-ttu-id="6b5c7-103">Procedimiento para proteger un servicio con un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="6b5c7-103">How to: Secure a Service with an X.509 Certificate</span></span>

<span data-ttu-id="6b5c7-104">La protección de un servicio con un certificado X. 509 es una técnica básica que utilizan la mayoría de los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6b5c7-104">Securing a service with an X.509 certificate is a basic technique that most bindings in Windows Communication Foundation (WCF) use.</span></span> <span data-ttu-id="6b5c7-105">En este tema se describen los pasos necesarios para configurar un servicio autoalojado con un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-105">This topic walks through the steps of configuring a self-hosted service with an X.509 certificate.</span></span>  
  
 <span data-ttu-id="6b5c7-106">Un requisito previo es un certificado válido que se puede utilizar para autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-106">A prerequisite is a valid certificate that can be used to authenticate the server.</span></span> <span data-ttu-id="6b5c7-107">Una entidad emisora de certificados de confianza debe emitir el certificado.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-107">The certificate must be issued to the server by a trusted certificate authority.</span></span> <span data-ttu-id="6b5c7-108">Si el certificado no es válido, cualquier cliente que intente usar el servicio no confiará en el servicio y, por tanto, no se realizará ninguna conexión.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-108">If the certificate is not valid, any client trying to use the service will not trust the service, and consequently no connection will be made.</span></span> <span data-ttu-id="6b5c7-109">Para obtener más información sobre el uso de certificados, consulte [trabajar con certificados](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6b5c7-109">For more information about using certificates, see [Working with Certificates](working-with-certificates.md).</span></span>  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a><span data-ttu-id="6b5c7-110">Configuración de un servicio con un certificado mediante código</span><span class="sxs-lookup"><span data-stu-id="6b5c7-110">To configure a service with a certificate using code</span></span>  
  
1. <span data-ttu-id="6b5c7-111">Cree el contrato de servicio y el servicio implementado.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-111">Create the service contract and the implemented service.</span></span> <span data-ttu-id="6b5c7-112">Para obtener más información, vea [diseñar e implementar servicios](../designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="6b5c7-112">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md).</span></span>  
  
2. <span data-ttu-id="6b5c7-113">Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-113">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3. <span data-ttu-id="6b5c7-114">Cree dos variables <xref:System.Type>, una para el tipo de contrato y otra para el contrato implementado, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-114">Create two <xref:System.Type> variables, one each for the contract type and the implemented contract, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4. <span data-ttu-id="6b5c7-115">Cree una instancia de la clase <xref:System.Uri> para la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-115">Create an instance of the <xref:System.Uri> class for the base address of the service.</span></span> <span data-ttu-id="6b5c7-116">Dado `WSHttpBinding` que utiliza el transporte http, el identificador uniforme de recursos (URI) debe comenzar con ese esquema o Windows Communication Foundation (WCF) producirá una excepción cuando se abra el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-116">Because the `WSHttpBinding` uses the HTTP transport, the Uniform Resource Identifier (URI) must begin with that schema, or Windows Communication Foundation (WCF) will throw an exception when the service is opened.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5. <span data-ttu-id="6b5c7-117">Cree una nueva instancia de la clase <xref:System.ServiceModel.ServiceHost> con la variable del tipo de contrato implementado y el URI.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-117">Create a new instance of the <xref:System.ServiceModel.ServiceHost> class with the implemented contract type variable and the URI.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6. <span data-ttu-id="6b5c7-118">Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> al servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-118">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> to the service using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span> <span data-ttu-id="6b5c7-119">Pase el contrato, enlace y una dirección del extremo al constructor, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-119">Pass the contract, binding, and an endpoint address to the constructor, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7. <span data-ttu-id="6b5c7-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-120">Optional.</span></span> <span data-ttu-id="6b5c7-121">Para recuperar los metadatos del servicio, cree un nuevo objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-121">To retrieve metadata from the service, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> object and set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8. <span data-ttu-id="6b5c7-122">Use el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para agregar al servicio el certificado válido.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-122">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to add the valid certificate to the service.</span></span> <span data-ttu-id="6b5c7-123">El método puede utilizar un método de varios para encontrar un certificado.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-123">The method can use one of several methods to find a certificate.</span></span> <span data-ttu-id="6b5c7-124">Este ejemplo usa la enumeración <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-124">This example uses the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> enumeration.</span></span> <span data-ttu-id="6b5c7-125">La enumeración especifica que el valor proporcionado es el nombre de la entidad a la que se emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-125">The enumeration specifies that the supplied value is the name of the entity that the certificate was issued to.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. <span data-ttu-id="6b5c7-126">Llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> para iniciar la escucha del servicio.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-126">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service listening.</span></span> <span data-ttu-id="6b5c7-127">Si está creando una aplicación de consola, llame al método <xref:System.Console.ReadLine%2A> para mantener el servicio en el estado de escucha.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-127">If you are creating a console application, call the <xref:System.Console.ReadLine%2A> method to keep the service in the listening state.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="6b5c7-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b5c7-128">Example</span></span>  

 <span data-ttu-id="6b5c7-129">El ejemplo siguiente utiliza el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> para configurar un servicio con un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-129">The following example uses the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method to configure a service with an X.509 certificate.</span></span>  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b5c7-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6b5c7-130">Compiling the Code</span></span>  

 <span data-ttu-id="6b5c7-131">Los espacios de nombres siguientes son necesarios para compilar el código:</span><span class="sxs-lookup"><span data-stu-id="6b5c7-131">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.Web.Services.Description>  
  
- <xref:System.Security.Cryptography.X509Certificates>  
  
- <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a><span data-ttu-id="6b5c7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b5c7-132">See also</span></span>

- [<span data-ttu-id="6b5c7-133">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="6b5c7-133">Working with Certificates</span></span>](working-with-certificates.md)
