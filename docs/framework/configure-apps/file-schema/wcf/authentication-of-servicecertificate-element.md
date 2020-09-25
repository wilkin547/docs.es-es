---
title: <authentication> del <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: c6f2578d85971740e5bd3d75151305a475187492
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201595"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="c2d01-102">\<authentication> del \<serviceCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="c2d01-102">\<authentication> of \<serviceCertificate> Element</span></span>

<span data-ttu-id="c2d01-103">Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="c2d01-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="c2d01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2d01-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2d01-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2d01-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c2d01-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2d01-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2d01-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2d01-107">Attributes</span></span>  
  
|<span data-ttu-id="c2d01-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c2d01-108">Attribute</span></span>|<span data-ttu-id="c2d01-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2d01-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="c2d01-110">customCertificateValidatorType</span></span>|<span data-ttu-id="c2d01-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="c2d01-111">String.</span></span> <span data-ttu-id="c2d01-112">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2d01-112">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="c2d01-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c2d01-113">certificateValidationMode</span></span>|<span data-ttu-id="c2d01-114">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="c2d01-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="c2d01-115">Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="c2d01-115">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="c2d01-116">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-116">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="c2d01-117">revocationMode</span><span class="sxs-lookup"><span data-stu-id="c2d01-117">revocationMode</span></span>|<span data-ttu-id="c2d01-118">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="c2d01-118">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="c2d01-119">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-119">The default is `Online`.</span></span>|  
|<span data-ttu-id="c2d01-120">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c2d01-120">trustedStoreLocation</span></span>|<span data-ttu-id="c2d01-121">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-121">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c2d01-122">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="c2d01-122">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="c2d01-123">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d01-123">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="c2d01-124">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-124">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="c2d01-125">Atributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="c2d01-125">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="c2d01-126">Value</span><span class="sxs-lookup"><span data-stu-id="c2d01-126">Value</span></span>|<span data-ttu-id="c2d01-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2d01-128">String</span><span class="sxs-lookup"><span data-stu-id="c2d01-128">String</span></span>|<span data-ttu-id="c2d01-129">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="c2d01-129">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="c2d01-130">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c2d01-130">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="c2d01-131">Value</span><span class="sxs-lookup"><span data-stu-id="c2d01-131">Value</span></span>|<span data-ttu-id="c2d01-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2d01-133">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c2d01-133">Enumeration</span></span>|<span data-ttu-id="c2d01-134">Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="c2d01-134">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="c2d01-135">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c2d01-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="c2d01-136">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="c2d01-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="c2d01-137">Value</span><span class="sxs-lookup"><span data-stu-id="c2d01-137">Value</span></span>|<span data-ttu-id="c2d01-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2d01-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c2d01-139">Enumeration</span></span>|<span data-ttu-id="c2d01-140">Uno de los valores siguientes: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="c2d01-140">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="c2d01-141">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c2d01-141">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="c2d01-142">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c2d01-142">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="c2d01-143">Value</span><span class="sxs-lookup"><span data-stu-id="c2d01-143">Value</span></span>|<span data-ttu-id="c2d01-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2d01-145">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c2d01-145">Enumeration</span></span>|<span data-ttu-id="c2d01-146">Uno de los valores siguientes: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c2d01-146">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="c2d01-147">El valor predeterminado es CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c2d01-147">The default is CurrentUser.</span></span> <span data-ttu-id="c2d01-148">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c2d01-148">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="c2d01-149">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c2d01-149">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2d01-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2d01-150">Child Elements</span></span>  

 <span data-ttu-id="c2d01-151">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c2d01-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2d01-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2d01-152">Parent Elements</span></span>  
  
|<span data-ttu-id="c2d01-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2d01-153">Element</span></span>|<span data-ttu-id="c2d01-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d01-154">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="c2d01-155">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="c2d01-155">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2d01-156">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2d01-156">Remarks</span></span>  

 <span data-ttu-id="c2d01-157">El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados.</span><span class="sxs-lookup"><span data-stu-id="c2d01-157">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="c2d01-158">De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="c2d01-158">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="c2d01-159">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="c2d01-159">This is the most secure mode.</span></span> <span data-ttu-id="c2d01-160">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="c2d01-160">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="c2d01-161">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="c2d01-161">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="c2d01-162">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-162">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="c2d01-163">También puede establecer el valor como `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="c2d01-163">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="c2d01-164">Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="c2d01-164">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="c2d01-165">Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="c2d01-165">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="c2d01-166">Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="c2d01-166">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="c2d01-167">El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="c2d01-167">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="c2d01-168">El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="c2d01-168">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="c2d01-169">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c2d01-169">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d01-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2d01-170">Example</span></span>  

 <span data-ttu-id="c2d01-171">El siguiente ejemplo realiza dos tareas:</span><span class="sxs-lookup"><span data-stu-id="c2d01-171">The following example does two tasks.</span></span> <span data-ttu-id="c2d01-172">En primer lugar, especifica un certificado de servicio para que el cliente lo utilice al comunicarse con puntos de conexión cuyo nombre de dominio está `www.contoso.com` por encima del protocolo http.</span><span class="sxs-lookup"><span data-stu-id="c2d01-172">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="c2d01-173">En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="c2d01-173">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c2d01-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2d01-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="c2d01-175">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="c2d01-175">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c2d01-176">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c2d01-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c2d01-177">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="c2d01-177">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="c2d01-178">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="c2d01-178">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c2d01-179">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c2d01-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
