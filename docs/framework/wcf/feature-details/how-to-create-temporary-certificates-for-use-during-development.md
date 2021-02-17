---
title: Procedimiento para crear certificados temporales que puedan usarse durante las operaciones de desarrollo
description: Obtenga información sobre cómo usar un cmdlet de PowerShell para crear dos certificados X. 509 temporales para su uso en el desarrollo de un servicio o cliente WCF seguro.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 45df7b2c4dad1aa84ad39ca38fba8d2ec16c8fb3
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100585355"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="f67e9-103">Procedimiento para crear certificados temporales que puedan usarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="f67e9-103">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="f67e9-104">Al desarrollar un servicio o cliente seguro mediante Windows Communication Foundation (WCF), a menudo es necesario proporcionar un certificado X. 509 que se usará como credencial.</span><span class="sxs-lookup"><span data-stu-id="f67e9-104">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="f67e9-105">El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo.</span><span class="sxs-lookup"><span data-stu-id="f67e9-105">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="f67e9-106">Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio.</span><span class="sxs-lookup"><span data-stu-id="f67e9-106">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="f67e9-107">Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f67e9-107">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="f67e9-108">El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f67e9-108">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="f67e9-109">En este tema se explican los pasos para crear estos dos certificados con el cmdlet [New-SelfSignedCertificate de](/powershell/module/pkiclient/new-selfsignedcertificate) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f67e9-109">This topic walks through the steps to create these two certificates using the PowerShell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f67e9-110">Los certificados generados por el cmdlet New-SelfSignedCertificate se proporcionan únicamente con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="f67e9-110">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="f67e9-111">Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f67e9-111">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="f67e9-112">Puede tratarse de un servidor de certificados de Windows Server de su organización o de un tercero.</span><span class="sxs-lookup"><span data-stu-id="f67e9-112">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="f67e9-113">De forma predeterminada, el cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) crea certificados que son autofirmados y que estos certificados no son seguros.</span><span class="sxs-lookup"><span data-stu-id="f67e9-113">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="f67e9-114">La colocación de los certificados autofirmados en el almacén de entidades de certificación raíz de confianza le permite crear un entorno de desarrollo que simula de forma más precisa el entorno de implementación.</span><span class="sxs-lookup"><span data-stu-id="f67e9-114">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="f67e9-115">Para obtener más información sobre la creación y el uso de certificados, consulte [trabajar con certificados](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f67e9-115">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="f67e9-116">Para obtener más información sobre el uso de un certificado como credencial, consulte [protección de servicios y clientes](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f67e9-116">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="f67e9-117">Para obtener un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [Authenticode Overviews and Tutorials (Información general y tutoriales de Authenticode)](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="f67e9-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="f67e9-118">Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada</span><span class="sxs-lookup"><span data-stu-id="f67e9-118">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="f67e9-119">El siguiente comando crea un certificado autofirmado con un nombre de sujeto "RootCA" en el almacén personal del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f67e9-119">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootCert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="f67e9-120">Necesitamos exportar el certificado a un archivo PFX para que se pueda importar en el punto en que se necesite en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="f67e9-120">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="f67e9-121">Cuando se exporta un certificado con la clave privada, se necesita una contraseña para protegerlo.</span><span class="sxs-lookup"><span data-stu-id="f67e9-121">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="f67e9-122">La contraseña se guarda en un `SecureString` y se usa el cmdlet [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) para exportar el certificado con la clave privada asociada a un archivo PFX.</span><span class="sxs-lookup"><span data-stu-id="f67e9-122">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="f67e9-123">También guardamos solo el certificado público en un archivo CRT mediante el cmdlet [Export-Certificate](/powershell/module/pkiclient/export-certificate) .</span><span class="sxs-lookup"><span data-stu-id="f67e9-123">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootCertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootCert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootCertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="f67e9-124">Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz</span><span class="sxs-lookup"><span data-stu-id="f67e9-124">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="f67e9-125">El siguiente comando crea un certificado firmado por el `RootCA` con un nombre de sujeto de "SignedByRootCA" mediante la clave privada del emisor.</span><span class="sxs-lookup"><span data-stu-id="f67e9-125">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="f67e9-126">Del mismo modo, guardamos el certificado firmado con clave privada en un archivo PFX y simplemente la clave pública en un archivo CRT.</span><span class="sxs-lookup"><span data-stu-id="f67e9-126">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootCertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="f67e9-127">Instalar un certificado en el almacén de entidades de certificación raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="f67e9-127">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="f67e9-128">Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="f67e9-128">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="f67e9-129">El equipo confía en todos los certificados firmados con el certificado en este punto.</span><span class="sxs-lookup"><span data-stu-id="f67e9-129">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="f67e9-130">Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="f67e9-130">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="f67e9-131">Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él.</span><span class="sxs-lookup"><span data-stu-id="f67e9-131">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="f67e9-132">Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f67e9-132">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="f67e9-133">Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.</span><span class="sxs-lookup"><span data-stu-id="f67e9-133">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="f67e9-134">Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="f67e9-134">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="f67e9-135">Abra el complemento del certificado.</span><span class="sxs-lookup"><span data-stu-id="f67e9-135">Open the certificate snap-in.</span></span> <span data-ttu-id="f67e9-136">Para más información, consulte [Visualización de certificados con el complemento MMC](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="f67e9-136">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="f67e9-137">Abra la carpeta para almacenar el certificado, el **Equipo local** o el **Usuario actual**.</span><span class="sxs-lookup"><span data-stu-id="f67e9-137">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="f67e9-138">Abra la carpeta **Entidades emisoras de certificados raíz de confianza** .</span><span class="sxs-lookup"><span data-stu-id="f67e9-138">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="f67e9-139">Haga clic con el botón secundario en la carpeta **Certificados** y haga clic en **Todas las tareas**, a continuación, haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f67e9-139">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="f67e9-140">Siga las instrucciones del asistente en pantalla para importar el archivo RootCA. pfx en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f67e9-140">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="f67e9-141">Uso de certificados con WCF</span><span class="sxs-lookup"><span data-stu-id="f67e9-141">Using certificates With WCF</span></span>

<span data-ttu-id="f67e9-142">Una vez que se han preparado los certificados temporales, puede usarlos para desarrollar soluciones WCF que especifiquen los certificados como un tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="f67e9-142">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="f67e9-143">Por ejemplo, en la siguiente configuración XML se especifica la seguridad de mensaje y un certificado como tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="f67e9-143">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="f67e9-144">Para especificar un certificado como tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="f67e9-144">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="f67e9-145">En el archivo de configuración de un servicio, use el código XML siguiente para establecer el modo de seguridad en mensaje y el tipo de credencial de cliente en certificado.</span><span class="sxs-lookup"><span data-stu-id="f67e9-145">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="f67e9-146">En el archivo de configuración de un cliente, use el código XML siguiente para especificar que el certificado se encuentra en el almacén del usuario y que se puede encontrar buscando el valor "CohoWinery" en el campo SubjectName.</span><span class="sxs-lookup"><span data-stu-id="f67e9-146">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="f67e9-147">Para obtener más información sobre el uso de certificados en WCF, consulte [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f67e9-147">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="f67e9-148">seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f67e9-148">.NET Framework security</span></span>

<span data-ttu-id="f67e9-149">Asegúrese de eliminar cualquier los certificados temporales de entidad emisora raíz de las carpetas **Entidades emisoras de certificados raíz de confianza** y **Personal** haciendo clic con el botón secundario en el certificado y, a continuación, haciendo clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f67e9-149">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f67e9-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f67e9-150">See also</span></span>

- [<span data-ttu-id="f67e9-151">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="f67e9-151">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="f67e9-152">Procedimiento para ver certificados con el complemento de MMC</span><span class="sxs-lookup"><span data-stu-id="f67e9-152">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="f67e9-153">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f67e9-153">Securing Services and Clients</span></span>](securing-services-and-clients.md)
