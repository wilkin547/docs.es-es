---
title: <certificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400551"
---
# <a name="certificate-element"></a><span data-ttu-id="91652-102">\<Certificate >, elemento</span><span class="sxs-lookup"><span data-stu-id="91652-102">\<certificate> Element</span></span>
<span data-ttu-id="91652-103">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="91652-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="91652-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91652-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91652-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91652-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91652-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91652-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="91652-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91652-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="91652-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91652-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="91652-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="91652-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="91652-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del mismo nivel**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="91652-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="91652-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de certificado**</span><span class="sxs-lookup"><span data-stu-id="91652-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91652-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91652-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91652-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91652-113">Attributes and Elements</span></span>  
 <span data-ttu-id="91652-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91652-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91652-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="91652-115">Attributes</span></span>  
  
|<span data-ttu-id="91652-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="91652-116">Attribute</span></span>|<span data-ttu-id="91652-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="91652-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="91652-118">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="91652-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="91652-119">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="91652-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="91652-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="91652-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="91652-121">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="91652-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="91652-122">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="91652-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91652-123">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="91652-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="91652-124">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="91652-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="91652-125">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="91652-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="91652-126">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="91652-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="91652-127">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="91652-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91652-128">Libreta Almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="91652-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="91652-129">AuthRoot Almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="91652-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="91652-130">CertificateAuthority Almacén de certificados para las entidades de certificación (CA) intermedias.</span><span class="sxs-lookup"><span data-stu-id="91652-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="91652-131">No permitidos Almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="91652-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="91652-132">Telefónica Almacén de certificados para Certificados personales.</span><span class="sxs-lookup"><span data-stu-id="91652-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="91652-133">Raíces Almacén de certificados para entidades de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="91652-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="91652-134">TrustedPeople Almacén de certificados para las personas y los recursos de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="91652-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="91652-135">TrustedPublisher Almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="91652-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="91652-136">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="91652-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="91652-137">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="91652-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="91652-138">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="91652-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91652-139">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="91652-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="91652-140">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="91652-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="91652-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="91652-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="91652-142">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="91652-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="91652-143">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="91652-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="91652-144">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="91652-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="91652-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="91652-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="91652-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="91652-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="91652-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="91652-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="91652-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="91652-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="91652-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="91652-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="91652-150">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="91652-150">-   FindByExtension</span></span><br /><span data-ttu-id="91652-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="91652-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="91652-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="91652-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="91652-153">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="91652-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="91652-154">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="91652-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91652-155">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91652-155">Child Elements</span></span>  
 <span data-ttu-id="91652-156">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91652-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91652-157">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91652-157">Parent Elements</span></span>  
  
|<span data-ttu-id="91652-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="91652-158">Element</span></span>|<span data-ttu-id="91652-159">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="91652-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91652-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="91652-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="91652-161">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="91652-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91652-162">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91652-162">Remarks</span></span>  
 <span data-ttu-id="91652-163">Este elemento de configuración contiene una instancia de X509Certificate2 que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="91652-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="91652-164">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="91652-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91652-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91652-165">Example</span></span>  
 <span data-ttu-id="91652-166">El código siguiente especifica cómo buscar el certificado usado en un escenario punto a punto.</span><span class="sxs-lookup"><span data-stu-id="91652-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="91652-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="91652-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="91652-168">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="91652-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="91652-169">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="91652-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="91652-170">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="91652-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="91652-171">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="91652-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="91652-172">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="91652-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
