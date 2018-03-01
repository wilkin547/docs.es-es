---
title: "Cómo crear un servicio que emplee un validador de certificado personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e0a48801b1d4674b81a0e4b54a80b69d026ce2af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="70077-102">Cómo crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="70077-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="70077-103">En este tema se muestra cómo implementar un validador del certificado personalizado y cómo configurar el cliente o credenciales del servicio para reemplazar la lógica de validación de certificado predeterminada por el validador del certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="70077-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="70077-104">Si se utiliza el certificado X.509 para autenticar un cliente o servicio, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza de forma predeterminada el almacén de certificados de Windows y Crypto API para validar el certificado y asegurarse que es de confianza.</span><span class="sxs-lookup"><span data-stu-id="70077-104">If the X.509 certificate is used to authenticate a client or service, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="70077-105">La funcionalidad integrada de validación del certificado no es suficiente y a veces se debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="70077-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="70077-106"> proporciona una manera sencilla de cambiar la lógica de validación permitiendo a los usuarios agregar un validador personalizado de certificado.</span><span class="sxs-lookup"><span data-stu-id="70077-106"> provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="70077-107">Si se especifica un validador de certificado personalizado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no utiliza la lógica de validación de certificado integrada, pero se basa  en el validador personalizado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="70077-107">If a custom certificate validator is specified, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="70077-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="70077-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="70077-109">Crear un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="70077-109">To create a custom certificate validator</span></span>  
  
1.  <span data-ttu-id="70077-110">Defina una clase nueva derivada a partir de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="70077-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2.  <span data-ttu-id="70077-111">Implemente el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> abstracto.</span><span class="sxs-lookup"><span data-stu-id="70077-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="70077-112">El certificado que se debe validar se pasa como un argumento al método.</span><span class="sxs-lookup"><span data-stu-id="70077-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="70077-113">Si el certificado pasado no es válido según la lógica de la validación, este método inicia <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="70077-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="70077-114">Si el certificado es válido, el método vuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="70077-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70077-115">Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="70077-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="70077-116">Especificar un validador de certificado personalizado en configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="70077-116">To specify a custom certificate validator in service configuration</span></span>  
  
1.  <span data-ttu-id="70077-117">Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento y un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-117">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="70077-118">Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="70077-118">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="70077-119">Agregar un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) a la `<behavior>` elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-119">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4.  <span data-ttu-id="70077-120">Agregue un elemento `<clientCertificate>` al elemento `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="70077-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5.  <span data-ttu-id="70077-121">Agregar un [ \<autenticación >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) a la `<clientCertificate>` elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-121">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6.  <span data-ttu-id="70077-122">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="70077-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="70077-123">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="70077-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7.  <span data-ttu-id="70077-124">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="70077-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="70077-125">Especificar un validador de certificado personalizado mediante la configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="70077-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1.  <span data-ttu-id="70077-126">Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento y un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-126">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="70077-127">Agregar un [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-127">Add an [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="70077-128">Agregue un elemento `<behavior>` y establezca el atributo `name` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="70077-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="70077-129">Agregar un [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70077-129">Add a [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5.  <span data-ttu-id="70077-130">Agregar un [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="70077-130">Add a [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6.  <span data-ttu-id="70077-131">Agregar un [ \<autenticación >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="70077-131">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7.  <span data-ttu-id="70077-132">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="70077-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8.  <span data-ttu-id="70077-133">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="70077-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="70077-134">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="70077-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="70077-135">Especificar un validador de certificado personalizado mediante el código en el servicio</span><span class="sxs-lookup"><span data-stu-id="70077-135">To specify a custom certificate validator using code on the service</span></span>  
  
1.  <span data-ttu-id="70077-136">Especifique el validador de certificado personalizado en la propiedad <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="70077-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="70077-137">Puede obtener acceso a las credenciales de servicio mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="70077-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2.  <span data-ttu-id="70077-138">Establezca la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="70077-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="70077-139">Especificar un validador de certificado personalizado mediante el código en el cliente</span><span class="sxs-lookup"><span data-stu-id="70077-139">To specify a custom certificate validator using code on the client</span></span>  
  
1.  <span data-ttu-id="70077-140">Especifique el validador de certificado personalizado mediante la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="70077-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="70077-141">Puede obtener acceso a las credenciales de cliente mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="70077-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="70077-142">(La clase de cliente generada por [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) siempre se deriva de la <xref:System.ServiceModel.ClientBase%601> clase.)</span><span class="sxs-lookup"><span data-stu-id="70077-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2.  <span data-ttu-id="70077-143">Establezca la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="70077-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70077-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70077-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70077-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="70077-145">Description</span></span>  
 <span data-ttu-id="70077-146">El ejemplo siguiente muestra una implementación de un validador de certificado personalizado y su uso en el servicio.</span><span class="sxs-lookup"><span data-stu-id="70077-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70077-147">Código</span><span class="sxs-lookup"><span data-stu-id="70077-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="70077-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="70077-148">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>
