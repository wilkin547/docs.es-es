---
title: <authentication> de <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: b96d53312d672eebd67de82f69cd9a0a2b5bd22e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117775"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="d0e44-102">\<autenticación > de \<serviceCertificate > elemento</span><span class="sxs-lookup"><span data-stu-id="d0e44-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="d0e44-103">Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="d0e44-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="d0e44-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0e44-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0e44-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d0e44-105">\<behaviors></span></span>  
<span data-ttu-id="d0e44-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="d0e44-106">endpointBehaviors section</span></span>  
<span data-ttu-id="d0e44-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d0e44-107">\<behavior></span></span>  
<span data-ttu-id="d0e44-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d0e44-108">\<clientCredentials></span></span>  
<span data-ttu-id="d0e44-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="d0e44-109">\<serviceCertificate></span></span>  
<span data-ttu-id="d0e44-110">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d0e44-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e44-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0e44-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0e44-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0e44-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d0e44-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0e44-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0e44-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0e44-114">Attributes</span></span>  
  
|<span data-ttu-id="d0e44-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d0e44-115">Attribute</span></span>|<span data-ttu-id="d0e44-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0e44-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="d0e44-117">customCertificateValidatorType</span></span>|<span data-ttu-id="d0e44-118">Cadena.</span><span class="sxs-lookup"><span data-stu-id="d0e44-118">String.</span></span> <span data-ttu-id="d0e44-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d0e44-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="d0e44-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="d0e44-120">certificateValidationMode</span></span>|<span data-ttu-id="d0e44-121">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d0e44-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="d0e44-122">Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="d0e44-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="d0e44-123">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="d0e44-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="d0e44-124">revocationMode</span></span>|<span data-ttu-id="d0e44-125">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="d0e44-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="d0e44-126">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="d0e44-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d0e44-127">trustedStoreLocation</span></span>|<span data-ttu-id="d0e44-128">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="d0e44-129">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e44-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="d0e44-130">Se realiza la validación contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="d0e44-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="d0e44-131">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="d0e44-132">Atributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="d0e44-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="d0e44-133">Valor</span><span class="sxs-lookup"><span data-stu-id="d0e44-133">Value</span></span>|<span data-ttu-id="d0e44-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e44-135">String</span><span class="sxs-lookup"><span data-stu-id="d0e44-135">String</span></span>|<span data-ttu-id="d0e44-136">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="d0e44-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="d0e44-137">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="d0e44-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="d0e44-138">Valor</span><span class="sxs-lookup"><span data-stu-id="d0e44-138">Value</span></span>|<span data-ttu-id="d0e44-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e44-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d0e44-140">Enumeration</span></span>|<span data-ttu-id="d0e44-141">Uno de los siguientes valores: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="d0e44-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="d0e44-142">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0e44-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="d0e44-143">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="d0e44-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="d0e44-144">Valor</span><span class="sxs-lookup"><span data-stu-id="d0e44-144">Value</span></span>|<span data-ttu-id="d0e44-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e44-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d0e44-146">Enumeration</span></span>|<span data-ttu-id="d0e44-147">Uno de los siguientes valores: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="d0e44-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="d0e44-148">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0e44-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="d0e44-149">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d0e44-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="d0e44-150">Valor</span><span class="sxs-lookup"><span data-stu-id="d0e44-150">Value</span></span>|<span data-ttu-id="d0e44-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e44-152">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d0e44-152">Enumeration</span></span>|<span data-ttu-id="d0e44-153">Uno de los siguientes valores: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="d0e44-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="d0e44-154">El valor predeterminado es CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="d0e44-154">The default is CurrentUser.</span></span> <span data-ttu-id="d0e44-155">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d0e44-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="d0e44-156">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="d0e44-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0e44-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0e44-157">Child Elements</span></span>  
 <span data-ttu-id="d0e44-158">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d0e44-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0e44-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0e44-159">Parent Elements</span></span>  
  
|<span data-ttu-id="d0e44-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0e44-160">Element</span></span>|<span data-ttu-id="d0e44-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e44-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0e44-162">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="d0e44-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="d0e44-163">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e44-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e44-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0e44-164">Remarks</span></span>  
 <span data-ttu-id="d0e44-165">El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados.</span><span class="sxs-lookup"><span data-stu-id="d0e44-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="d0e44-166">De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d0e44-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="d0e44-167">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="d0e44-167">This is the most secure mode.</span></span> <span data-ttu-id="d0e44-168">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="d0e44-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="d0e44-169">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="d0e44-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="d0e44-170">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="d0e44-171">También puede establecer el valor como `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="d0e44-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="d0e44-172">Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="d0e44-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="d0e44-173">Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="d0e44-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="d0e44-174">Para obtener más información, vea [Cómo: Crear un servicio que emplee un validador de certificado personalizado](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="d0e44-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="d0e44-175">El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="d0e44-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="d0e44-176">El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="d0e44-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="d0e44-177">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0e44-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e44-178">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0e44-178">Example</span></span>  
 <span data-ttu-id="d0e44-179">El siguiente ejemplo realiza dos tareas:</span><span class="sxs-lookup"><span data-stu-id="d0e44-179">The following example does two tasks.</span></span> <span data-ttu-id="d0e44-180">Primero especifica un certificado de servicio para el cliente que se usará al comunicarse con puntos de conexión cuyo nombre de dominio es `www.contoso.com` a través del protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="d0e44-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="d0e44-181">En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="d0e44-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="d0e44-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0e44-182">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="d0e44-183">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0e44-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d0e44-184">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="d0e44-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d0e44-185">Cómo: Crear un servicio que emplee un validador de certificado personalizada</span><span class="sxs-lookup"><span data-stu-id="d0e44-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="d0e44-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d0e44-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="d0e44-187">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d0e44-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="d0e44-188">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d0e44-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
