---
description: 'Más información sobre: <authentication> del <clientCertificate> elemento'
title: <authentication> del <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 346e1012fd9d799b093be15381aebbc026ea2591
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749901"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="6314c-103">\<authentication> del \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="6314c-103">\<authentication> of \<clientCertificate> Element</span></span>

<span data-ttu-id="6314c-104">Especifica los comportamientos de autenticación para los certificados de cliente utilizados por un servicio.</span><span class="sxs-lookup"><span data-stu-id="6314c-104">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="6314c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6314c-105">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6314c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6314c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6314c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6314c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6314c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6314c-108">Attributes</span></span>  
  
|<span data-ttu-id="6314c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="6314c-109">Attribute</span></span>|<span data-ttu-id="6314c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6314c-111">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="6314c-111">customCertificateValidatorType</span></span>|<span data-ttu-id="6314c-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="6314c-112">Optional string.</span></span> <span data-ttu-id="6314c-113">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6314c-113">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="6314c-114">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="6314c-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="6314c-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6314c-115">certificateValidationMode</span></span>|<span data-ttu-id="6314c-116">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="6314c-116">Optional enumeration.</span></span> <span data-ttu-id="6314c-117">Especifica uno de los modos usados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="6314c-117">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="6314c-118">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="6314c-118">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="6314c-119">Si se establece en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="6314c-119">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="6314c-120">De manera predeterminada, es <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6314c-120">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="6314c-121">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="6314c-121">includeWindowsGroups</span></span>|<span data-ttu-id="6314c-122">Opcional booleano.</span><span class="sxs-lookup"><span data-stu-id="6314c-122">Optional Boolean.</span></span> <span data-ttu-id="6314c-123">Especifica si los grupos de Windows están incluidos en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6314c-123">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="6314c-124">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="6314c-124">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="6314c-125">Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="6314c-125">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="6314c-126">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="6314c-126">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="6314c-127">booleano.</span><span class="sxs-lookup"><span data-stu-id="6314c-127">Boolean.</span></span> <span data-ttu-id="6314c-128">Especifica si el cliente puede estar asignado a una identidad de Windows utilizando el certificado.</span><span class="sxs-lookup"><span data-stu-id="6314c-128">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="6314c-129">Active Directory debe estar habilitado para ello.</span><span class="sxs-lookup"><span data-stu-id="6314c-129">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="6314c-130">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6314c-130">revocationMode</span></span>|<span data-ttu-id="6314c-131">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="6314c-131">Optional enumeration.</span></span> <span data-ttu-id="6314c-132">Uno de los modos utilizados para comprobar listas de certificados revocadas (RCL).</span><span class="sxs-lookup"><span data-stu-id="6314c-132">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="6314c-133">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="6314c-133">The default is `Online`.</span></span> <span data-ttu-id="6314c-134">Se omite este valor al usar la seguridad de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="6314c-134">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="6314c-135">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6314c-135">trustedStoreLocation</span></span>|<span data-ttu-id="6314c-136">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="6314c-136">Optional enumeration.</span></span> <span data-ttu-id="6314c-137">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6314c-137">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6314c-138">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="6314c-138">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="6314c-139">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="6314c-139">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="6314c-140">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6314c-140">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="6314c-141">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="6314c-141">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="6314c-142">Value</span><span class="sxs-lookup"><span data-stu-id="6314c-142">Value</span></span>|<span data-ttu-id="6314c-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6314c-144">String</span><span class="sxs-lookup"><span data-stu-id="6314c-144">String</span></span>|<span data-ttu-id="6314c-145">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="6314c-145">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="6314c-146">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6314c-146">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="6314c-147">Value</span><span class="sxs-lookup"><span data-stu-id="6314c-147">Value</span></span>|<span data-ttu-id="6314c-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6314c-149">Enumeración</span><span class="sxs-lookup"><span data-stu-id="6314c-149">Enumeration</span></span>|<span data-ttu-id="6314c-150">Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="6314c-150">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="6314c-151">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6314c-151">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="6314c-152">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="6314c-152">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="6314c-153">Value</span><span class="sxs-lookup"><span data-stu-id="6314c-153">Value</span></span>|<span data-ttu-id="6314c-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6314c-155">Enumeración</span><span class="sxs-lookup"><span data-stu-id="6314c-155">Enumeration</span></span>|<span data-ttu-id="6314c-156">Uno de los valores siguientes: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="6314c-156">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="6314c-157">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6314c-157">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="6314c-158">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6314c-158">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="6314c-159">Value</span><span class="sxs-lookup"><span data-stu-id="6314c-159">Value</span></span>|<span data-ttu-id="6314c-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6314c-161">Enumeración</span><span class="sxs-lookup"><span data-stu-id="6314c-161">Enumeration</span></span>|<span data-ttu-id="6314c-162">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6314c-162">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6314c-163">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6314c-163">The default is `CurrentUser`.</span></span> <span data-ttu-id="6314c-164">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="6314c-164">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="6314c-165">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6314c-165">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6314c-166">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6314c-166">Child Elements</span></span>  

 <span data-ttu-id="6314c-167">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6314c-167">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6314c-168">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6314c-168">Parent Elements</span></span>  
  
|<span data-ttu-id="6314c-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="6314c-169">Element</span></span>|<span data-ttu-id="6314c-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="6314c-170">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="6314c-171">Define un certificado X.509 que se usa para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="6314c-171">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6314c-172">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6314c-172">Remarks</span></span>  

 <span data-ttu-id="6314c-173">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="6314c-173">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="6314c-174">Le permite personalizar cómo se autentican los clientes.</span><span class="sxs-lookup"><span data-stu-id="6314c-174">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="6314c-175">Puede establecer el atributo `certificateValidationMode` en `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`.</span><span class="sxs-lookup"><span data-stu-id="6314c-175">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="6314c-176">De forma predeterminada, el nivel se establece en `ChainTrust` , que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una *entidad de certificación raíz* en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="6314c-176">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="6314c-177">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="6314c-177">This is the most secure mode.</span></span> <span data-ttu-id="6314c-178">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="6314c-178">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="6314c-179">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="6314c-179">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="6314c-180">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6314c-180">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="6314c-181">También puede establecer el valor en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="6314c-181">You can also set the value to `Custom`.</span></span> <span data-ttu-id="6314c-182">Cuando se establezca en el valor `Custom`, también debe establecer el atributo `customCertificateValidatorType` en un ensamblado y tipo utilizados para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="6314c-182">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="6314c-183">Para crear su propio validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.</span><span class="sxs-lookup"><span data-stu-id="6314c-183">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="6314c-184">Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="6314c-184">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6314c-185">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6314c-185">Example</span></span>  

 <span data-ttu-id="6314c-186">El código siguiente especifica un certificado X.509 y un tipo de validación personalizado en el elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="6314c-186">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6314c-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="6314c-187">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="6314c-188">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="6314c-188">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6314c-189">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="6314c-189">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="6314c-190">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="6314c-190">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
