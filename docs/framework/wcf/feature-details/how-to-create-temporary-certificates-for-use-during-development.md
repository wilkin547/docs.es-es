---
title: 'Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5a096fd6e052fc744af5cee1ab0d322e1daafe6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="1aeca-102">Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="1aeca-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="1aeca-103">Cuando se desarrolla un servicio seguro o cliente utilizando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], a menudo es necesario proporcionar un certificado X.509 que se utilizará como una credencial.</span><span class="sxs-lookup"><span data-stu-id="1aeca-103">When developing a secure service or client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="1aeca-104">El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo.</span><span class="sxs-lookup"><span data-stu-id="1aeca-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="1aeca-105">Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio.</span><span class="sxs-lookup"><span data-stu-id="1aeca-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="1aeca-106">Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1aeca-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="1aeca-107">El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="1aeca-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="1aeca-108">En este tema se describen los pasos para crear estos dos certificados con [Certificate Creation Tool (Herramienta de creación de certificados) (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), proporcionada por el SDK de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1aeca-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1aeca-109">Los certificados generados por la herramienta de creación de certificados sólo se proporcionan para pruebas.</span><span class="sxs-lookup"><span data-stu-id="1aeca-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="1aeca-110">Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="1aeca-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="1aeca-111">Esto podría ser de un servidor de certificado [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] en su organización o de un tercero.</span><span class="sxs-lookup"><span data-stu-id="1aeca-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="1aeca-112">De forma predeterminada, el [Makecert.exe (herramienta de creación de certificados)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) crea certificados cuya entidad emisora raíz se denomina "Agencia raíz **."**</span><span class="sxs-lookup"><span data-stu-id="1aeca-112">By default, the [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency **."**</span></span> <span data-ttu-id="1aeca-113">Dado que la "Agencia raíz" no está en el almacén Entidades emisoras de certificados raíz de confianza, estos certificados no son seguros.</span><span class="sxs-lookup"><span data-stu-id="1aeca-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="1aeca-114">Crear un certificado con firma automática que se coloca en el almacén Entidades emisoras de certificados raíz de confianza le permite crear un entorno de desarrollo que simula su entorno de distribución.</span><span class="sxs-lookup"><span data-stu-id="1aeca-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 <span data-ttu-id="1aeca-115">Para obtener más información sobre la creación y uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1aeca-115">For more information about creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="1aeca-116">Para obtener más información sobre el uso de un certificado como credencial, vea [protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1aeca-116">For more information about using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="1aeca-117">Para obtener un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [Authenticode Overviews and Tutorials (Información general y tutoriales de Authenticode)](http://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="1aeca-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="1aeca-118">Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada</span><span class="sxs-lookup"><span data-stu-id="1aeca-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="1aeca-119">Utilice la herramienta MakeCert.exe con los modificadores siguientes:</span><span class="sxs-lookup"><span data-stu-id="1aeca-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="1aeca-120">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-120">`-n` `subjectName`.</span></span> <span data-ttu-id="1aeca-121">Especifica el nombre del sujeto.</span><span class="sxs-lookup"><span data-stu-id="1aeca-121">Specifies the subject name.</span></span> <span data-ttu-id="1aeca-122">La convención es prefijar el nombre sujeto con "CN = " para "Nombre Común."</span><span class="sxs-lookup"><span data-stu-id="1aeca-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="1aeca-123">`-r`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-123">`-r`.</span></span> <span data-ttu-id="1aeca-124">Especifica que el certificado se firmará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1aeca-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="1aeca-125">`-sv` `privateKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="1aeca-126">Especifica el archivo que contiene el contenedor de clave privada.</span><span class="sxs-lookup"><span data-stu-id="1aeca-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="1aeca-127">Por ejemplo, el comando siguiente crea un certificado firmado automáticamente con un nombre sujeto de "CN=TempCA."</span><span class="sxs-lookup"><span data-stu-id="1aeca-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="1aeca-128">Le solicitarán que proporcione una contraseña para proteger la clave privada.</span><span class="sxs-lookup"><span data-stu-id="1aeca-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="1aeca-129">Esta contraseña es necesaria para crear un certificado firmado por este certificado raíz.</span><span class="sxs-lookup"><span data-stu-id="1aeca-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="1aeca-130">Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz</span><span class="sxs-lookup"><span data-stu-id="1aeca-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="1aeca-131">Utilice la herramienta MakeCert.exe con los modificadores siguientes:</span><span class="sxs-lookup"><span data-stu-id="1aeca-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="1aeca-132">`-sk` `subjectKey`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="1aeca-133">La ubicación del contenedor de la clave del sujeto que contiene la clave privada.</span><span class="sxs-lookup"><span data-stu-id="1aeca-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="1aeca-134">Si no existe un contenedor de claves, se creará uno.</span><span class="sxs-lookup"><span data-stu-id="1aeca-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="1aeca-135">Si no se utiliza ninguna de las opciones - sk o - sv, se crea un contenedor de claves llamado JoeSoft de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1aeca-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="1aeca-136">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-136">`-n` `subjectName`.</span></span> <span data-ttu-id="1aeca-137">Especifica el nombre del sujeto.</span><span class="sxs-lookup"><span data-stu-id="1aeca-137">Specifies the subject name.</span></span> <span data-ttu-id="1aeca-138">La convención es prefijar el nombre sujeto con "CN = " para "Nombre Común."</span><span class="sxs-lookup"><span data-stu-id="1aeca-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="1aeca-139">`-iv` `issuerKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="1aeca-140">Especifica el archivo de clave privada .del emisor.</span><span class="sxs-lookup"><span data-stu-id="1aeca-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="1aeca-141">`-ic` `issuerCertFile`.</span><span class="sxs-lookup"><span data-stu-id="1aeca-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="1aeca-142">Especifica la ubicación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="1aeca-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="1aeca-143">Por ejemplo, el comando siguiente crea un certificado firmado por el certificado de entidad emisora raíz `TempCA` con un nombre sujeto de `"CN=SignedByCA"` utilizando la clave privada del emisor.</span><span class="sxs-lookup"><span data-stu-id="1aeca-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="1aeca-144">Instalar un certificado en el almacén de entidades de certificación raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="1aeca-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="1aeca-145">Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="1aeca-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="1aeca-146">El equipo confía en todos los certificados firmados con el certificado en este punto.</span><span class="sxs-lookup"><span data-stu-id="1aeca-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="1aeca-147">Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="1aeca-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="1aeca-148">Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él.</span><span class="sxs-lookup"><span data-stu-id="1aeca-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="1aeca-149">Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1aeca-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="1aeca-150">Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.</span><span class="sxs-lookup"><span data-stu-id="1aeca-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="1aeca-151">Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="1aeca-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="1aeca-152">Abra el complemento del certificado.</span><span class="sxs-lookup"><span data-stu-id="1aeca-152">Open the certificate snap-in.</span></span> <span data-ttu-id="1aeca-153">Para obtener más información, consulte [Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="1aeca-153">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="1aeca-154">Abra la carpeta para almacenar el certificado, el **Equipo local** o el **Usuario actual**.</span><span class="sxs-lookup"><span data-stu-id="1aeca-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="1aeca-155">Abra la carpeta **Entidades emisoras de certificados raíz de confianza** .</span><span class="sxs-lookup"><span data-stu-id="1aeca-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="1aeca-156">Haga clic con el botón secundario en la carpeta **Certificados** y haga clic en **Todas las tareas**, a continuación, haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="1aeca-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="1aeca-157">Siga las instrucciones del asistente en pantalla para importar TempCa.cer en el almacén.</span><span class="sxs-lookup"><span data-stu-id="1aeca-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="1aeca-158">Uso de certificados con WCF</span><span class="sxs-lookup"><span data-stu-id="1aeca-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="1aeca-159">Una vez que se han preparado los certificados temporales, puede usarlos para desarrollar soluciones WCF que especifiquen los certificados como un tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="1aeca-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="1aeca-160">Por ejemplo, en la siguiente configuración XML se especifica la seguridad de mensaje y un certificado como tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="1aeca-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="1aeca-161">Para especificar un certificado como tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="1aeca-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="1aeca-162">En el archivo de configuración de un servicio, use el código XML siguiente para establecer el modo de seguridad en mensaje y el tipo de credencial de cliente en certificado.</span><span class="sxs-lookup"><span data-stu-id="1aeca-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 <span data-ttu-id="1aeca-163">En el archivo de configuración para un cliente, utilice el siguiente código XML para especificar que el certificado está en el almacén del usuario y puede encontrarse por campo SubjectName para el valor "CohoWinery".</span><span class="sxs-lookup"><span data-stu-id="1aeca-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="1aeca-164">Para obtener más información sobre el uso de certificados en WCF, consulte [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1aeca-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1aeca-165">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1aeca-165">.NET Framework Security</span></span>  
 <span data-ttu-id="1aeca-166">Asegúrese de eliminar cualquier los certificados temporales de entidad emisora raíz de las carpetas **Entidades emisoras de certificados raíz de confianza** y **Personal** haciendo clic con el botón secundario en el certificado y, a continuación, haciendo clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1aeca-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aeca-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aeca-167">See Also</span></span>  
 [<span data-ttu-id="1aeca-168">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="1aeca-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1aeca-169">Visualización de certificados con el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="1aeca-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="1aeca-170">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1aeca-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
