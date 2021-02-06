---
description: 'Más información acerca de: <certificate> elemento'
title: <certificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 3f67435d86f19f81c1f6fe1fe2a9a8afbef69e53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639138"
---
# <a name="certificate-element"></a><span data-ttu-id="3f719-103">\<certificate> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="3f719-103">\<certificate> Element</span></span>

<span data-ttu-id="3f719-104">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3f719-104">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="3f719-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f719-105">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f719-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3f719-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3f719-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3f719-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f719-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f719-108">Attributes</span></span>  
  
|<span data-ttu-id="3f719-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="3f719-109">Attribute</span></span>|<span data-ttu-id="3f719-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f719-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="3f719-111">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="3f719-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3f719-112">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="3f719-112">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="3f719-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3f719-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="3f719-114">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="3f719-114">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="3f719-115">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f719-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f719-116">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="3f719-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="3f719-117">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="3f719-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="3f719-118">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3f719-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="3f719-119">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="3f719-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="3f719-120">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f719-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f719-121">-AddressBook: almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f719-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="3f719-122">-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="3f719-122">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="3f719-123">-CertificateAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.</span><span class="sxs-lookup"><span data-stu-id="3f719-123">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="3f719-124">-No permitido: almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="3f719-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="3f719-125">-Mi: almacén de certificados para Certificados personales.</span><span class="sxs-lookup"><span data-stu-id="3f719-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="3f719-126">-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="3f719-126">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="3f719-127">-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="3f719-127">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="3f719-128">-TrustedPublisher: almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="3f719-128">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="3f719-129">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="3f719-129">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="3f719-130">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="3f719-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="3f719-131">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f719-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f719-132">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="3f719-132">-   FindByThumbPrint</span></span><br /><span data-ttu-id="3f719-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="3f719-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="3f719-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3f719-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="3f719-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="3f719-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="3f719-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3f719-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="3f719-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="3f719-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="3f719-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="3f719-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="3f719-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="3f719-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="3f719-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="3f719-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="3f719-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="3f719-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="3f719-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="3f719-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="3f719-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="3f719-143">-   FindByExtension</span></span><br /><span data-ttu-id="3f719-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="3f719-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="3f719-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="3f719-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="3f719-146">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="3f719-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="3f719-147">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="3f719-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f719-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3f719-148">Child Elements</span></span>  

 <span data-ttu-id="3f719-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3f719-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f719-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3f719-150">Parent Elements</span></span>  
  
|<span data-ttu-id="3f719-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f719-151">Element</span></span>|<span data-ttu-id="3f719-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f719-152">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="3f719-153">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3f719-153">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f719-154">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f719-154">Remarks</span></span>  

 <span data-ttu-id="3f719-155">Este elemento de configuración contiene una instancia de X509Certificate2 que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3f719-155">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="3f719-156">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="3f719-156">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f719-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f719-157">Example</span></span>  

 <span data-ttu-id="3f719-158">El código siguiente especifica cómo buscar el certificado usado en un escenario punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3f719-158">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f719-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f719-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="3f719-160">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="3f719-160">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3f719-161">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="3f719-161">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="3f719-162">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3f719-162">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="3f719-163">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3f719-163">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="3f719-164">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="3f719-164">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
