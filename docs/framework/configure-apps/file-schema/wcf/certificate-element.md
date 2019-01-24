---
title: '&lt;certificate&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: d1449cc6c40ae16190bacf378df3bd60c49d060c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538328"
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="d3b66-102">&lt;certificate&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="d3b66-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="d3b66-103">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d3b66-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="d3b66-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d3b66-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3b66-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d3b66-105">\<behaviors></span></span>  
<span data-ttu-id="d3b66-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d3b66-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d3b66-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d3b66-107">\<behavior></span></span>  
<span data-ttu-id="d3b66-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d3b66-108">\<clientCredentials></span></span>  
<span data-ttu-id="d3b66-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="d3b66-109">\<peer></span></span>  
<span data-ttu-id="d3b66-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="d3b66-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b66-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3b66-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3b66-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d3b66-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d3b66-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d3b66-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3b66-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3b66-114">Attributes</span></span>  
  
|<span data-ttu-id="d3b66-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d3b66-115">Attribute</span></span>|<span data-ttu-id="d3b66-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3b66-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="d3b66-117">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="d3b66-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="d3b66-118">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="d3b66-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="d3b66-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d3b66-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="d3b66-120">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="d3b66-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="d3b66-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3b66-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d3b66-122">-LocalMachine: almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="d3b66-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="d3b66-123">-CurrentUser: almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d3b66-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="d3b66-124">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d3b66-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="d3b66-125">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="d3b66-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="d3b66-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3b66-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d3b66-127">-   AddressBook: Almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d3b66-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="d3b66-128">-AuthRoot: Almacén de certificados para entidades de certificación de terceros (CAs).</span><span class="sxs-lookup"><span data-stu-id="d3b66-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="d3b66-129">-   CertificateAuthority: Almacén de certificados para entidades de certificación intermedias (CAs).</span><span class="sxs-lookup"><span data-stu-id="d3b66-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="d3b66-130">-No permitido: Almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="d3b66-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="d3b66-131">-Mi: Almacén de certificados para los certificados personales.</span><span class="sxs-lookup"><span data-stu-id="d3b66-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="d3b66-132">-Raíz: Almacén de certificados para entidades de certificación raíz de confianza (CA).</span><span class="sxs-lookup"><span data-stu-id="d3b66-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="d3b66-133">-TrustedPeople: Almacén de certificados de personas de confianza directa y recursos.</span><span class="sxs-lookup"><span data-stu-id="d3b66-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="d3b66-134">-   TrustedPublisher: Almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="d3b66-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="d3b66-135">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="d3b66-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="d3b66-136">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d3b66-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="d3b66-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3b66-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d3b66-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="d3b66-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="d3b66-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="d3b66-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="d3b66-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="d3b66-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="d3b66-141">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="d3b66-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="d3b66-142">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="d3b66-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="d3b66-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="d3b66-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="d3b66-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="d3b66-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="d3b66-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="d3b66-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="d3b66-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="d3b66-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="d3b66-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b66-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="d3b66-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="d3b66-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="d3b66-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="d3b66-149">-   FindByExtension</span></span><br /><span data-ttu-id="d3b66-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="d3b66-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="d3b66-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="d3b66-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="d3b66-152">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="d3b66-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="d3b66-153">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="d3b66-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3b66-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3b66-154">Child Elements</span></span>  
 <span data-ttu-id="d3b66-155">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d3b66-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3b66-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d3b66-156">Parent Elements</span></span>  
  
|<span data-ttu-id="d3b66-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3b66-157">Element</span></span>|<span data-ttu-id="d3b66-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3b66-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3b66-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="d3b66-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="d3b66-160">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d3b66-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3b66-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3b66-161">Remarks</span></span>  
 <span data-ttu-id="d3b66-162">Este elemento de configuración contiene una instancia de X509Certificate2 que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d3b66-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="d3b66-163">Para obtener más información acerca de la programación de punto a punto, vea [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="d3b66-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b66-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3b66-164">Example</span></span>  
 <span data-ttu-id="d3b66-165">El código siguiente especifica cómo buscar el certificado usado en un escenario punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d3b66-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d3b66-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3b66-166">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="d3b66-167">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="d3b66-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d3b66-168">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="d3b66-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="d3b66-169">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="d3b66-169">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="d3b66-170">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="d3b66-170">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="d3b66-171">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="d3b66-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
