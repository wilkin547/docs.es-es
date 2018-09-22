---
title: 'Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 2d0301b040d0fd9865eaf5c3f96fe320ccfd8488
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46698589"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="f49a1-102">Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="f49a1-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="f49a1-103">Al desarrollar un servicio seguro o cliente mediante Windows Communication Foundation (WCF), a menudo es necesario proporcionar un certificado X.509 que se usará como una credencial.</span><span class="sxs-lookup"><span data-stu-id="f49a1-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="f49a1-104">El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo.</span><span class="sxs-lookup"><span data-stu-id="f49a1-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="f49a1-105">Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio.</span><span class="sxs-lookup"><span data-stu-id="f49a1-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="f49a1-106">Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f49a1-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="f49a1-107">El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f49a1-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="f49a1-108">En este tema se describe los pasos para crear estos dos certificados mediante el Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f49a1-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f49a1-109">Los certificados que genera el cmdlet New-SelfSignedCertificate se proporcionan únicamente con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="f49a1-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="f49a1-110">Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f49a1-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="f49a1-111">Esto podría ser de un servidor de certificados de Windows Server en su organización o un tercero.</span><span class="sxs-lookup"><span data-stu-id="f49a1-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="f49a1-112">De forma predeterminada, el [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet crea certificados autofirmados y estos certificados no son seguros.</span><span class="sxs-lookup"><span data-stu-id="f49a1-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="f49a1-113">Almacén de colocación de los certificados autofirmados en las entidades de certificación raíz de confianza permite crear un entorno de desarrollo que simula el entorno de implementación.</span><span class="sxs-lookup"><span data-stu-id="f49a1-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="f49a1-114">Para obtener más información sobre la creación y uso de certificados, consulte [trabajar con certificados](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f49a1-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="f49a1-115">Para obtener más información sobre el uso de un certificado como credencial, vea [proteger servicios y clientes](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f49a1-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="f49a1-116">Para ver un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [información general de Authenticode y tutoriales](https://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="f49a1-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="f49a1-117">Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada</span><span class="sxs-lookup"><span data-stu-id="f49a1-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="f49a1-118">El siguiente comando crea un certificado autofirmado con un nombre de sujeto de "RootCA" en el almacén Personal de usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f49a1-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```

<span data-ttu-id="f49a1-119">Es necesario exportar el certificado a un archivo PFX, por lo que puede importarse a cuando sea necesario en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="f49a1-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="f49a1-120">Al exportar un certificado con la clave privada, se necesita una contraseña para protegerla.</span><span class="sxs-lookup"><span data-stu-id="f49a1-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="f49a1-121">Se guarda la contraseña en un `SecureString` y usar el [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet para exportar el certificado con la clave privada asociada a un archivo PFX.</span><span class="sxs-lookup"><span data-stu-id="f49a1-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="f49a1-122">También guardamos simplemente el certificado público en un archivo de CRT mediante el [Exportar certificado](/powershell/module/pkiclient/export-certificate) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f49a1-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="f49a1-123">Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz</span><span class="sxs-lookup"><span data-stu-id="f49a1-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="f49a1-124">El siguiente comando crea un certificado firmado por la `RootCA` con un nombre de sujeto de "SignedByRootCA" mediante la clave privada del emisor.</span><span class="sxs-lookup"><span data-stu-id="f49a1-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="f49a1-125">De forma similar, guardamos el certificado de firma con la clave privada en un archivo PFX y solo la clave pública en un archivo de CRT.</span><span class="sxs-lookup"><span data-stu-id="f49a1-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="f49a1-126">Instalar un certificado en el almacén de entidades de certificación raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="f49a1-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="f49a1-127">Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="f49a1-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="f49a1-128">El equipo confía en todos los certificados firmados con el certificado en este punto.</span><span class="sxs-lookup"><span data-stu-id="f49a1-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="f49a1-129">Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="f49a1-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="f49a1-130">Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él.</span><span class="sxs-lookup"><span data-stu-id="f49a1-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="f49a1-131">Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f49a1-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="f49a1-132">Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.</span><span class="sxs-lookup"><span data-stu-id="f49a1-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="f49a1-133">Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="f49a1-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="f49a1-134">Abra el complemento del certificado.</span><span class="sxs-lookup"><span data-stu-id="f49a1-134">Open the certificate snap-in.</span></span> <span data-ttu-id="f49a1-135">Para obtener más información, vea [Cómo: Ver certificados con el complemento de MMC](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="f49a1-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="f49a1-136">Abra la carpeta para almacenar el certificado, el **Equipo local** o el **Usuario actual**.</span><span class="sxs-lookup"><span data-stu-id="f49a1-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="f49a1-137">Abra la carpeta **Entidades emisoras de certificados raíz de confianza** .</span><span class="sxs-lookup"><span data-stu-id="f49a1-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="f49a1-138">Haga clic con el botón secundario en la carpeta **Certificados** y haga clic en **Todas las tareas**, a continuación, haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f49a1-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="f49a1-139">Siga las instrucciones del asistente en pantalla para importar TempCa.cer en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f49a1-139">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="f49a1-140">Uso de certificados con WCF</span><span class="sxs-lookup"><span data-stu-id="f49a1-140">Using certificates With WCF</span></span>

<span data-ttu-id="f49a1-141">Una vez que se han preparado los certificados temporales, puede usarlos para desarrollar soluciones WCF que especifiquen los certificados como un tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="f49a1-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="f49a1-142">Por ejemplo, en la siguiente configuración XML se especifica la seguridad de mensaje y un certificado como tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="f49a1-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="f49a1-143">Para especificar un certificado como tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="f49a1-143">To specify a certificate as the client credential type</span></span>

- <span data-ttu-id="f49a1-144">En el archivo de configuración de un servicio, use el código XML siguiente para establecer el modo de seguridad en mensaje y el tipo de credencial de cliente en certificado.</span><span class="sxs-lookup"><span data-stu-id="f49a1-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

<span data-ttu-id="f49a1-145">En el archivo de configuración para un cliente, use el siguiente código XML para especificar que el certificado es se encuentre en el almacén del usuario y puede encontrarlo buscando el campo SubjectName para el valor "CohoWinery".</span><span class="sxs-lookup"><span data-stu-id="f49a1-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="f49a1-146">Para obtener más información sobre el uso de certificados en WCF, vea [trabajar con certificados](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f49a1-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="f49a1-147">seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f49a1-147">.NET Framework security</span></span>

<span data-ttu-id="f49a1-148">Asegúrese de eliminar cualquier los certificados temporales de entidad emisora raíz de las carpetas **Entidades emisoras de certificados raíz de confianza** y **Personal** haciendo clic con el botón secundario en el certificado y, a continuación, haciendo clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f49a1-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f49a1-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49a1-149">See also</span></span>

- [<span data-ttu-id="f49a1-150">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="f49a1-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="f49a1-151">Visualización de certificados con el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="f49a1-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="f49a1-152">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f49a1-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)