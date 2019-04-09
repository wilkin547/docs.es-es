---
title: Filtrar para crear un servicio que emplee un validador de certificado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: 7c2eb820a7e087d99ebd2c463db6e10595f7c1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119631"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="ba7d5-102">Filtrar para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="ba7d5-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="ba7d5-103">En este tema se muestra cómo implementar un validador del certificado personalizado y cómo configurar el cliente o credenciales del servicio para reemplazar la lógica de validación de certificado predeterminada por el validador del certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="ba7d5-104">Si se utiliza el certificado X.509 para autenticar un cliente o servicio, Windows Communication Foundation (WCF) de forma predeterminada usa el almacén de certificados de Windows y Crypto API para validar el certificado y para asegurarse de que es de confianza.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="ba7d5-105">La funcionalidad integrada de validación del certificado no es suficiente y a veces se debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="ba7d5-106">WCF ofrece una manera fácil de cambiar la lógica de validación permitiendo a los usuarios agregar un validador de certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="ba7d5-107">Si se especifica un validador de certificado personalizado, WCF no utiliza la lógica de validación de certificado integrada, pero se basa en el validador personalizado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ba7d5-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ba7d5-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="ba7d5-109">Crear un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="ba7d5-109">To create a custom certificate validator</span></span>  
  
1.  <span data-ttu-id="ba7d5-110">Defina una clase nueva derivada a partir de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2.  <span data-ttu-id="ba7d5-111">Implemente el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> abstracto.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="ba7d5-112">El certificado que se debe validar se pasa como un argumento al método.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="ba7d5-113">Si el certificado pasado no es válido según la lógica de la validación, este método inicia <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="ba7d5-114">Si el certificado es válido, el método vuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba7d5-115">Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="ba7d5-116">Especificar un validador de certificado personalizado en configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="ba7d5-116">To specify a custom certificate validator in service configuration</span></span>  
  
1.  <span data-ttu-id="ba7d5-117">Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento y un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-117">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="ba7d5-118">Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-118">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="ba7d5-119">Agregar un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) a la `<behavior>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-119">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4.  <span data-ttu-id="ba7d5-120">Agregue un elemento `<clientCertificate>` al elemento `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5.  <span data-ttu-id="ba7d5-121">Agregar un [ \<autenticación >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) a la `<clientCertificate>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-121">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6.  <span data-ttu-id="ba7d5-122">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="ba7d5-123">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7.  <span data-ttu-id="ba7d5-124">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="ba7d5-125">Especificar un validador de certificado personalizado mediante la configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="ba7d5-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1.  <span data-ttu-id="ba7d5-126">Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento y un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-126">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="ba7d5-127">Agregar un [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-127">Add an [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="ba7d5-128">Agregue un elemento `<behavior>` y establezca el atributo `name` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="ba7d5-129">Agregar un [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-129">Add a [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5.  <span data-ttu-id="ba7d5-130">Agregar un [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="ba7d5-130">Add a [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6.  <span data-ttu-id="ba7d5-131">Agregar un [ \<autenticación >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-131">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7.  <span data-ttu-id="ba7d5-132">Defina el atributo `customCertificateValidatorType` en el tipo de validador.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8.  <span data-ttu-id="ba7d5-133">Defina el atributo `certificateValidationMode` a `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="ba7d5-134">El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="ba7d5-135">Especificar un validador de certificado personalizado mediante el código en el servicio</span><span class="sxs-lookup"><span data-stu-id="ba7d5-135">To specify a custom certificate validator using code on the service</span></span>  
  
1.  <span data-ttu-id="ba7d5-136">Especifique el validador de certificado personalizado en la propiedad <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="ba7d5-137">Puede obtener acceso a las credenciales de servicio mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2.  <span data-ttu-id="ba7d5-138">Establezca la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="ba7d5-139">Especificar un validador de certificado personalizado mediante el código en el cliente</span><span class="sxs-lookup"><span data-stu-id="ba7d5-139">To specify a custom certificate validator using code on the client</span></span>  
  
1.  <span data-ttu-id="ba7d5-140">Especifique el validador de certificado personalizado mediante la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="ba7d5-141">Puede obtener acceso a las credenciales de cliente mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="ba7d5-142">(La clase de cliente generada por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) siempre se deriva de la <xref:System.ServiceModel.ClientBase%601> clase.)</span><span class="sxs-lookup"><span data-stu-id="ba7d5-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2.  <span data-ttu-id="ba7d5-143">Establezca la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba7d5-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba7d5-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ba7d5-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba7d5-145">Description</span></span>  
 <span data-ttu-id="ba7d5-146">El ejemplo siguiente muestra una implementación de un validador de certificado personalizado y su uso en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ba7d5-147">Código</span><span class="sxs-lookup"><span data-stu-id="ba7d5-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ba7d5-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba7d5-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
