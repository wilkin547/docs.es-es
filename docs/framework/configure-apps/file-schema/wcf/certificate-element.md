---
title: <certificate> Elemento
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: eea8130911ca3780a6e4e753c17877e58c50b139
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164273"
---
# <a name="certificate-element"></a><span data-ttu-id="a4f0e-102">\<certificado > elemento</span><span class="sxs-lookup"><span data-stu-id="a4f0e-102">\<certificate> Element</span></span>
<span data-ttu-id="a4f0e-103">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="a4f0e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a4f0e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4f0e-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a4f0e-105">\<behaviors></span></span>  
<span data-ttu-id="a4f0e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a4f0e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a4f0e-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a4f0e-107">\<behavior></span></span>  
<span data-ttu-id="a4f0e-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a4f0e-108">\<clientCredentials></span></span>  
<span data-ttu-id="a4f0e-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="a4f0e-109">\<peer></span></span>  
<span data-ttu-id="a4f0e-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="a4f0e-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f0e-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4f0e-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4f0e-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a4f0e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a4f0e-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4f0e-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4f0e-114">Attributes</span></span>  
  
|<span data-ttu-id="a4f0e-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="a4f0e-115">Attribute</span></span>|<span data-ttu-id="a4f0e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4f0e-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a4f0e-117">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a4f0e-118">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="a4f0e-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a4f0e-120">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="a4f0e-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4f0e-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a4f0e-122">-LocalMachine: almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a4f0e-123">-CurrentUser: almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a4f0e-124">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="a4f0e-125">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="a4f0e-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4f0e-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a4f0e-127">-   AddressBook: Almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a4f0e-128">-AuthRoot: Almacén de certificados para entidades de certificación de terceros (CAs).</span><span class="sxs-lookup"><span data-stu-id="a4f0e-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a4f0e-129">-   CertificateAuthority: Almacén de certificados para entidades de certificación intermedias (CAs).</span><span class="sxs-lookup"><span data-stu-id="a4f0e-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="a4f0e-130">-No permitido: Almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a4f0e-131">-Mi: Almacén de certificados para los certificados personales.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a4f0e-132">-Raíz: Almacén de certificados para entidades de certificación raíz de confianza (CA).</span><span class="sxs-lookup"><span data-stu-id="a4f0e-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="a4f0e-133">-TrustedPeople: Almacén de certificados de personas de confianza directa y recursos.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="a4f0e-134">-   TrustedPublisher: Almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="a4f0e-135">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="a4f0e-136">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a4f0e-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4f0e-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a4f0e-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a4f0e-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a4f0e-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a4f0e-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="a4f0e-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a4f0e-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a4f0e-141">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a4f0e-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="a4f0e-142">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a4f0e-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a4f0e-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a4f0e-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a4f0e-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a4f0e-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="a4f0e-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a4f0e-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a4f0e-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a4f0e-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="a4f0e-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a4f0e-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a4f0e-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a4f0e-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a4f0e-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a4f0e-149">-   FindByExtension</span></span><br /><span data-ttu-id="a4f0e-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a4f0e-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a4f0e-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a4f0e-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a4f0e-152">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="a4f0e-153">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4f0e-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a4f0e-154">Child Elements</span></span>  
 <span data-ttu-id="a4f0e-155">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4f0e-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4f0e-156">Parent Elements</span></span>  
  
|<span data-ttu-id="a4f0e-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4f0e-157">Element</span></span>|<span data-ttu-id="a4f0e-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4f0e-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4f0e-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="a4f0e-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a4f0e-160">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4f0e-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4f0e-161">Remarks</span></span>  
 <span data-ttu-id="a4f0e-162">Este elemento de configuración contiene una instancia de X509Certificate2 que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="a4f0e-163">Para obtener más información acerca de la programación de punto a punto, vea [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a4f0e-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4f0e-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4f0e-164">Example</span></span>  
 <span data-ttu-id="a4f0e-165">El código siguiente especifica cómo buscar el certificado usado en un escenario punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a4f0e-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a4f0e-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4f0e-166">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="a4f0e-167">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="a4f0e-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a4f0e-168">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="a4f0e-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="a4f0e-169">Autenticación del mensaje del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a4f0e-169">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="a4f0e-170">Autenticación personalizada de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a4f0e-170">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="a4f0e-171">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a4f0e-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
