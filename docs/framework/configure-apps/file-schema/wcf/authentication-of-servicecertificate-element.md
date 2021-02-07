---
description: 'Más información sobre: <authentication> del <serviceCertificate> elemento'
title: <authentication> del <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 35a94f4f9c089f86aef38e7e9a1115a7cd22a325
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749888"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="8d134-103">\<authentication> del \<serviceCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="8d134-103">\<authentication> of \<serviceCertificate> Element</span></span>

<span data-ttu-id="8d134-104">Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="8d134-104">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="8d134-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d134-105">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d134-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8d134-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8d134-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8d134-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d134-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8d134-108">Attributes</span></span>  
  
|<span data-ttu-id="8d134-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d134-109">Attribute</span></span>|<span data-ttu-id="8d134-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d134-111">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="8d134-111">customCertificateValidatorType</span></span>|<span data-ttu-id="8d134-112">String.</span><span class="sxs-lookup"><span data-stu-id="8d134-112">String.</span></span> <span data-ttu-id="8d134-113">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8d134-113">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="8d134-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="8d134-114">certificateValidationMode</span></span>|<span data-ttu-id="8d134-115">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="8d134-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="8d134-116">Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="8d134-116">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="8d134-117">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="8d134-117">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="8d134-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="8d134-118">revocationMode</span></span>|<span data-ttu-id="8d134-119">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="8d134-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="8d134-120">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="8d134-120">The default is `Online`.</span></span>|  
|<span data-ttu-id="8d134-121">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="8d134-121">trustedStoreLocation</span></span>|<span data-ttu-id="8d134-122">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="8d134-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="8d134-123">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="8d134-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="8d134-124">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="8d134-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="8d134-125">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="8d134-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="8d134-126">Atributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="8d134-126">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="8d134-127">Value</span><span class="sxs-lookup"><span data-stu-id="8d134-127">Value</span></span>|<span data-ttu-id="8d134-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d134-129">String</span><span class="sxs-lookup"><span data-stu-id="8d134-129">String</span></span>|<span data-ttu-id="8d134-130">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="8d134-130">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="8d134-131">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="8d134-131">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="8d134-132">Value</span><span class="sxs-lookup"><span data-stu-id="8d134-132">Value</span></span>|<span data-ttu-id="8d134-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d134-134">Enumeración</span><span class="sxs-lookup"><span data-stu-id="8d134-134">Enumeration</span></span>|<span data-ttu-id="8d134-135">Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="8d134-135">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="8d134-136">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="8d134-136">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="8d134-137">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="8d134-137">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="8d134-138">Value</span><span class="sxs-lookup"><span data-stu-id="8d134-138">Value</span></span>|<span data-ttu-id="8d134-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d134-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="8d134-140">Enumeration</span></span>|<span data-ttu-id="8d134-141">Uno de los valores siguientes: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="8d134-141">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="8d134-142">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="8d134-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="8d134-143">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="8d134-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="8d134-144">Value</span><span class="sxs-lookup"><span data-stu-id="8d134-144">Value</span></span>|<span data-ttu-id="8d134-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d134-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="8d134-146">Enumeration</span></span>|<span data-ttu-id="8d134-147">Uno de los valores siguientes: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="8d134-147">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="8d134-148">El valor predeterminado es CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="8d134-148">The default is CurrentUser.</span></span> <span data-ttu-id="8d134-149">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="8d134-149">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="8d134-150">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="8d134-150">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d134-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8d134-151">Child Elements</span></span>  

 <span data-ttu-id="8d134-152">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8d134-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d134-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8d134-153">Parent Elements</span></span>  
  
|<span data-ttu-id="8d134-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="8d134-154">Element</span></span>|<span data-ttu-id="8d134-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d134-155">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="8d134-156">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="8d134-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d134-157">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d134-157">Remarks</span></span>  

 <span data-ttu-id="8d134-158">El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados.</span><span class="sxs-lookup"><span data-stu-id="8d134-158">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="8d134-159">De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="8d134-159">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="8d134-160">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="8d134-160">This is the most secure mode.</span></span> <span data-ttu-id="8d134-161">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="8d134-161">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="8d134-162">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="8d134-162">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="8d134-163">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="8d134-163">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="8d134-164">También puede establecer el valor como `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="8d134-164">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="8d134-165">Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="8d134-165">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="8d134-166">Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="8d134-166">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="8d134-167">Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="8d134-167">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="8d134-168">El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="8d134-168">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="8d134-169">El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="8d134-169">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="8d134-170">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="8d134-170">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d134-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d134-171">Example</span></span>  

 <span data-ttu-id="8d134-172">El siguiente ejemplo realiza dos tareas:</span><span class="sxs-lookup"><span data-stu-id="8d134-172">The following example does two tasks.</span></span> <span data-ttu-id="8d134-173">En primer lugar, especifica un certificado de servicio para que el cliente lo utilice al comunicarse con puntos de conexión cuyo nombre de dominio está `www.contoso.com` por encima del protocolo http.</span><span class="sxs-lookup"><span data-stu-id="8d134-173">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="8d134-174">En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8d134-174">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d134-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d134-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="8d134-176">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="8d134-176">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8d134-177">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="8d134-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8d134-178">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="8d134-178">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="8d134-179">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="8d134-179">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8d134-180">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8d134-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
