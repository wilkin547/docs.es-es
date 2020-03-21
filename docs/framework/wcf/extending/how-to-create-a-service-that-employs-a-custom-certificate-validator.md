---
title: Cómo crear un servicio que emplee un validador de certificado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: af1bb9b2ff793f6e6854c1b253dd445a35a5076f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185574"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="e4205-102">Cómo crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="e4205-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="e4205-103">En este tema se muestra cómo implementar un validador del certificado personalizado y cómo configurar el cliente o credenciales del servicio para reemplazar la lógica de validación de certificado predeterminada por el validador del certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4205-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="e4205-104">Si el certificado X.509 se usa para autenticar un cliente o servicio, Windows Communication Foundation (WCF) usa de forma predeterminada el almacén de certificados de Windows y la API de cifrado para validar el certificado y para asegurarse de que es de confianza.</span><span class="sxs-lookup"><span data-stu-id="e4205-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="e4205-105">La funcionalidad integrada de validación del certificado no es suficiente y a veces se debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="e4205-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="e4205-106">WCF proporciona una manera fácil de cambiar la lógica de validación al permitir a los usuarios agregar un validador de certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4205-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="e4205-107">Si se especifica un validador de certificado personalizado, WCF no usa la lógica de validación de certificados integrada, pero se basa en el validador personalizado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e4205-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e4205-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e4205-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="e4205-109">Crear un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="e4205-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="e4205-110">Defina una clase nueva derivada a partir de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e4205-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="e4205-111">Implemente el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> abstracto.</span><span class="sxs-lookup"><span data-stu-id="e4205-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="e4205-112">El certificado que se debe validar se pasa como un argumento al método.</span><span class="sxs-lookup"><span data-stu-id="e4205-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="e4205-113">Si el certificado pasado no es válido según la lógica de la validación, este método inicia <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="e4205-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="e4205-114">Si el certificado es válido, el método vuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e4205-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e4205-115">Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4205-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="e4205-116">Especificar un validador de certificado personalizado en configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="e4205-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="e4205-117">Agregue un [ \<elemento>comportamientos](../../configure-apps/file-schema/wcf/behaviors.md) y un [ \<>serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) al [ \<elemento>system.serviceModel.](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e4205-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="e4205-118">Agregue [ \<](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un comportamiento>`name` y establezca el atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="e4205-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="e4205-119">Agregue un [ \<>serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) al `<behavior>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e4205-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="e4205-120">Agregue un elemento `<clientCertificate>` al elemento `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="e4205-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="e4205-121">Agregue [ \<](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) un>`<clientCertificate>` de autenticación al elemento.</span><span class="sxs-lookup"><span data-stu-id="e4205-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="e4205-122">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="e4205-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="e4205-123">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="e4205-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="e4205-124">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e4205-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="e4205-125">Especificar un validador de certificado personalizado mediante la configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="e4205-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="e4205-126">Agregue un [ \<elemento>comportamientos](../../configure-apps/file-schema/wcf/behaviors.md) y un [ \<>serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) al [ \<elemento>system.serviceModel.](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e4205-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="e4205-127">Agregue [ \<un elemento endpointBehaviors>.](../../configure-apps/file-schema/wcf/endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e4205-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="e4205-128">Agregue un elemento  y establezca el atributo  en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="e4205-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="e4205-129">Agregue un [ \<elemento de>clientCredentials.](../../configure-apps/file-schema/wcf/clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e4205-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="e4205-130">Agregue un [ \<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="e4205-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="e4205-131">Agregue [ \<](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) una>de autenticación como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4205-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="e4205-132">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="e4205-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="e4205-133">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e4205-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="e4205-134">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="e4205-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="e4205-135">Especificar un validador de certificado personalizado mediante el código en el servicio</span><span class="sxs-lookup"><span data-stu-id="e4205-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="e4205-136">Especifique el validador de certificado personalizado en la propiedad <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4205-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="e4205-137">Puede obtener acceso a las credenciales de servicio mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4205-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="e4205-138">Establezca la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="e4205-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="e4205-139">Especificar un validador de certificado personalizado mediante el código en el cliente</span><span class="sxs-lookup"><span data-stu-id="e4205-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="e4205-140">Especifique el validador de certificado personalizado mediante la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4205-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="e4205-141">Puede obtener acceso a las credenciales de cliente mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4205-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="e4205-142">(La clase de cliente generada por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) siempre deriva de la <xref:System.ServiceModel.ClientBase%601> clase.)</span><span class="sxs-lookup"><span data-stu-id="e4205-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="e4205-143">Establezca la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="e4205-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4205-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4205-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e4205-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4205-145">Description</span></span>  
 <span data-ttu-id="e4205-146">El ejemplo siguiente muestra una implementación de un validador de certificado personalizado y su uso en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e4205-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e4205-147">Código</span><span class="sxs-lookup"><span data-stu-id="e4205-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e4205-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4205-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
