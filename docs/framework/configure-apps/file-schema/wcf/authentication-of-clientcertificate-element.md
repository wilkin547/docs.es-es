---
title: <authentication>del <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 99084f6b7afbdd8586ee706cd6ec44b349d81ff2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398266"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="f3cbe-102">\<authentication>del \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="f3cbe-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="f3cbe-103">Especifica los comportamientos de autenticación para los certificados de cliente utilizados por un servicio.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="f3cbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3cbe-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3cbe-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f3cbe-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f3cbe-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3cbe-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3cbe-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3cbe-107">Attributes</span></span>  
  
|<span data-ttu-id="f3cbe-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f3cbe-108">Attribute</span></span>|<span data-ttu-id="f3cbe-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3cbe-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="f3cbe-110">customCertificateValidatorType</span></span>|<span data-ttu-id="f3cbe-111">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-111">Optional string.</span></span> <span data-ttu-id="f3cbe-112">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="f3cbe-113">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="f3cbe-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f3cbe-114">certificateValidationMode</span></span>|<span data-ttu-id="f3cbe-115">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-115">Optional enumeration.</span></span> <span data-ttu-id="f3cbe-116">Especifica uno de los modos usados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-116">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="f3cbe-117">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-117">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="f3cbe-118">Si se establece en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-118">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="f3cbe-119">De manera predeterminada, es <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-119">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="f3cbe-120">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="f3cbe-120">includeWindowsGroups</span></span>|<span data-ttu-id="f3cbe-121">Opcional booleano.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-121">Optional Boolean.</span></span> <span data-ttu-id="f3cbe-122">Especifica si los grupos de Windows están incluidos en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-122">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="f3cbe-123">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-123">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="f3cbe-124">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-124">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="f3cbe-125">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="f3cbe-125">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="f3cbe-126">booleano.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-126">Boolean.</span></span> <span data-ttu-id="f3cbe-127">Especifica si el cliente puede estar asignado a una identidad de Windows utilizando el certificado.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-127">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="f3cbe-128">Active Directory debe estar habilitado para ello.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-128">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="f3cbe-129">revocationMode</span><span class="sxs-lookup"><span data-stu-id="f3cbe-129">revocationMode</span></span>|<span data-ttu-id="f3cbe-130">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-130">Optional enumeration.</span></span> <span data-ttu-id="f3cbe-131">Uno de los modos utilizados para comprobar listas de certificados revocadas (RCL).</span><span class="sxs-lookup"><span data-stu-id="f3cbe-131">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="f3cbe-132">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-132">The default is `Online`.</span></span> <span data-ttu-id="f3cbe-133">Se omite este valor al usar la seguridad de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-133">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="f3cbe-134">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f3cbe-134">trustedStoreLocation</span></span>|<span data-ttu-id="f3cbe-135">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-135">Optional enumeration.</span></span> <span data-ttu-id="f3cbe-136">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="f3cbe-137">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-137">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="f3cbe-138">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-138">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="f3cbe-139">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-139">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="f3cbe-140">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="f3cbe-140">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="f3cbe-141">Value</span><span class="sxs-lookup"><span data-stu-id="f3cbe-141">Value</span></span>|<span data-ttu-id="f3cbe-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3cbe-143">String</span><span class="sxs-lookup"><span data-stu-id="f3cbe-143">String</span></span>|<span data-ttu-id="f3cbe-144">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-144">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="f3cbe-145">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f3cbe-145">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="f3cbe-146">Value</span><span class="sxs-lookup"><span data-stu-id="f3cbe-146">Value</span></span>|<span data-ttu-id="f3cbe-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3cbe-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f3cbe-148">Enumeration</span></span>|<span data-ttu-id="f3cbe-149">Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-149">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="f3cbe-150">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f3cbe-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="f3cbe-151">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="f3cbe-151">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="f3cbe-152">Value</span><span class="sxs-lookup"><span data-stu-id="f3cbe-152">Value</span></span>|<span data-ttu-id="f3cbe-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3cbe-154">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f3cbe-154">Enumeration</span></span>|<span data-ttu-id="f3cbe-155">Uno de los valores siguientes: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-155">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="f3cbe-156">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f3cbe-156">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="f3cbe-157">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f3cbe-157">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="f3cbe-158">Value</span><span class="sxs-lookup"><span data-stu-id="f3cbe-158">Value</span></span>|<span data-ttu-id="f3cbe-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3cbe-160">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f3cbe-160">Enumeration</span></span>|<span data-ttu-id="f3cbe-161">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-161">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="f3cbe-162">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-162">The default is `CurrentUser`.</span></span> <span data-ttu-id="f3cbe-163">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-163">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="f3cbe-164">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-164">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3cbe-165">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f3cbe-165">Child Elements</span></span>  
 <span data-ttu-id="f3cbe-166">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-166">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3cbe-167">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3cbe-167">Parent Elements</span></span>  
  
|<span data-ttu-id="f3cbe-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3cbe-168">Element</span></span>|<span data-ttu-id="f3cbe-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3cbe-169">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="f3cbe-170">Define un certificado X.509 que se usa para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-170">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3cbe-171">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3cbe-171">Remarks</span></span>  
 <span data-ttu-id="f3cbe-172">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-172">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="f3cbe-173">Le permite personalizar cómo se autentican los clientes.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-173">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="f3cbe-174">Puede establecer el atributo `certificateValidationMode` en `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-174">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="f3cbe-175">De forma predeterminada, el nivel se establece en `ChainTrust` , que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una *entidad de certificación raíz* en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-175">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="f3cbe-176">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-176">This is the most secure mode.</span></span> <span data-ttu-id="f3cbe-177">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-177">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="f3cbe-178">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-178">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="f3cbe-179">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-179">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="f3cbe-180">También puede establecer el valor en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-180">You can also set the value to `Custom`.</span></span> <span data-ttu-id="f3cbe-181">Cuando se establezca en el valor `Custom`, también debe establecer el atributo `customCertificateValidatorType` en un ensamblado y tipo utilizados para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-181">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="f3cbe-182">Para crear su propio validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-182">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="f3cbe-183">Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="f3cbe-183">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cbe-184">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cbe-184">Example</span></span>  
 <span data-ttu-id="f3cbe-185">El código siguiente especifica un certificado X.509 y un tipo de validación personalizado en el elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="f3cbe-185">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="f3cbe-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3cbe-186">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="f3cbe-187">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f3cbe-187">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f3cbe-188">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="f3cbe-188">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="f3cbe-189">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="f3cbe-189">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
