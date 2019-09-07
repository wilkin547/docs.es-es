---
title: <authentication>del <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398226"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="f7288-102">\<> de autenticación \<del elemento de > serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="f7288-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="f7288-103">Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="f7288-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="f7288-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7288-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f7288-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f7288-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f7288-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f7288-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="f7288-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7288-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="f7288-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de autenticación**</span><span class="sxs-lookup"><span data-stu-id="f7288-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7288-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7288-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7288-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7288-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f7288-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7288-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7288-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7288-115">Attributes</span></span>  
  
|<span data-ttu-id="f7288-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="f7288-116">Attribute</span></span>|<span data-ttu-id="f7288-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7288-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="f7288-118">customCertificateValidatorType</span></span>|<span data-ttu-id="f7288-119">Cadena.</span><span class="sxs-lookup"><span data-stu-id="f7288-119">String.</span></span> <span data-ttu-id="f7288-120">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f7288-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="f7288-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f7288-121">certificateValidationMode</span></span>|<span data-ttu-id="f7288-122">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7288-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="f7288-123">Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="f7288-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="f7288-124">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f7288-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="f7288-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="f7288-125">revocationMode</span></span>|<span data-ttu-id="f7288-126">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="f7288-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="f7288-127">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="f7288-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="f7288-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f7288-128">trustedStoreLocation</span></span>|<span data-ttu-id="f7288-129">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f7288-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="f7288-130">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="f7288-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="f7288-131">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="f7288-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="f7288-132">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f7288-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="f7288-133">Atributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="f7288-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="f7288-134">Value</span><span class="sxs-lookup"><span data-stu-id="f7288-134">Value</span></span>|<span data-ttu-id="f7288-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7288-136">string</span><span class="sxs-lookup"><span data-stu-id="f7288-136">String</span></span>|<span data-ttu-id="f7288-137">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="f7288-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="f7288-138">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f7288-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="f7288-139">Valor</span><span class="sxs-lookup"><span data-stu-id="f7288-139">Value</span></span>|<span data-ttu-id="f7288-140">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7288-141">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f7288-141">Enumeration</span></span>|<span data-ttu-id="f7288-142">Uno de los siguientes valores: None, confianza, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="f7288-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="f7288-143">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f7288-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="f7288-144">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="f7288-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="f7288-145">Value</span><span class="sxs-lookup"><span data-stu-id="f7288-145">Value</span></span>|<span data-ttu-id="f7288-146">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7288-147">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f7288-147">Enumeration</span></span>|<span data-ttu-id="f7288-148">Uno de los siguientes valores: Nocheck, en línea, sin conexión.</span><span class="sxs-lookup"><span data-stu-id="f7288-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="f7288-149">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f7288-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="f7288-150">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f7288-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="f7288-151">Value</span><span class="sxs-lookup"><span data-stu-id="f7288-151">Value</span></span>|<span data-ttu-id="f7288-152">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7288-153">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f7288-153">Enumeration</span></span>|<span data-ttu-id="f7288-154">Uno de los siguientes valores: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="f7288-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="f7288-155">El valor predeterminado es CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="f7288-155">The default is CurrentUser.</span></span> <span data-ttu-id="f7288-156">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f7288-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="f7288-157">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="f7288-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7288-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7288-158">Child Elements</span></span>  
 <span data-ttu-id="f7288-159">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7288-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7288-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7288-160">Parent Elements</span></span>  
  
|<span data-ttu-id="f7288-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7288-161">Element</span></span>|<span data-ttu-id="f7288-162">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f7288-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7288-163">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f7288-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="f7288-164">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="f7288-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7288-165">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7288-165">Remarks</span></span>  
 <span data-ttu-id="f7288-166">El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados.</span><span class="sxs-lookup"><span data-stu-id="f7288-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="f7288-167">De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="f7288-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="f7288-168">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="f7288-168">This is the most secure mode.</span></span> <span data-ttu-id="f7288-169">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="f7288-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="f7288-170">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="f7288-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="f7288-171">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f7288-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="f7288-172">También puede establecer el valor como `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="f7288-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="f7288-173">Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="f7288-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="f7288-174">Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="f7288-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="f7288-175">Para obtener más información, consulte [Cómo Cree un servicio que emplee un validador](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)de certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="f7288-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="f7288-176">El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="f7288-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="f7288-177">El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="f7288-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="f7288-178">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f7288-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7288-179">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7288-179">Example</span></span>  
 <span data-ttu-id="f7288-180">El siguiente ejemplo realiza dos tareas:</span><span class="sxs-lookup"><span data-stu-id="f7288-180">The following example does two tasks.</span></span> <span data-ttu-id="f7288-181">En primer lugar, especifica un certificado de servicio para que el cliente lo utilice al comunicarse con puntos de `www.contoso.com` conexión cuyo nombre de dominio está por encima del protocolo http.</span><span class="sxs-lookup"><span data-stu-id="f7288-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="f7288-182">En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f7288-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7288-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7288-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="f7288-184">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7288-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f7288-185">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="f7288-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f7288-186">Procedimientos: Crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="f7288-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="f7288-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="f7288-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="f7288-188">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f7288-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f7288-189">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f7288-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
