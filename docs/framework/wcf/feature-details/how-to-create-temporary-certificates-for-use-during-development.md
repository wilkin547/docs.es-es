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
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Procedimiento para crear certificados temporales que puedan usarse durante las operaciones de desarrollo

Al desarrollar un servicio o cliente seguro mediante Windows Communication Foundation (WCF), a menudo es necesario proporcionar un certificado X. 509 que se usará como credencial. El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo. Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio. Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad. El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual. En este tema se explican los pasos para crear estos dos certificados con el cmdlet [New-SelfSignedCertificate de](/powershell/module/pkiclient/new-selfsignedcertificate) PowerShell.

> [!IMPORTANT]
> Los certificados generados por el cmdlet New-SelfSignedCertificate se proporcionan únicamente con fines de prueba. Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación. Puede tratarse de un servidor de certificados de Windows Server de su organización o de un tercero.
>
> De forma predeterminada, el cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) crea certificados que son autofirmados y que estos certificados no son seguros. La colocación de los certificados autofirmados en el almacén de entidades de certificación raíz de confianza le permite crear un entorno de desarrollo que simula de forma más precisa el entorno de implementación.

 Para obtener más información sobre la creación y el uso de certificados, consulte [trabajar con certificados](working-with-certificates.md). Para obtener más información sobre el uso de un certificado como credencial, consulte [protección de servicios y clientes](securing-services-and-clients.md). Para obtener un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [Authenticode Overviews and Tutorials (Información general y tutoriales de Authenticode)](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada

El siguiente comando crea un certificado autofirmado con un nombre de sujeto "RootCA" en el almacén personal del usuario actual.

```powershell
$rootCert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

Necesitamos exportar el certificado a un archivo PFX para que se pueda importar en el punto en que se necesite en un paso posterior. Cuando se exporta un certificado con la clave privada, se necesita una contraseña para protegerlo. La contraseña se guarda en un `SecureString` y se usa el cmdlet [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) para exportar el certificado con la clave privada asociada a un archivo PFX. También guardamos solo el certificado público en un archivo CRT mediante el cmdlet [Export-Certificate](/powershell/module/pkiclient/export-certificate) .

```powershell
[System.Security.SecureString]$rootCertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootCert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootCertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz

El siguiente comando crea un certificado firmado por el `RootCA` con un nombre de sujeto de "SignedByRootCA" mediante la clave privada del emisor.

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

Del mismo modo, guardamos el certificado firmado con clave privada en un archivo PFX y simplemente la clave pública en un archivo CRT.

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootCertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Instalar un certificado en el almacén de entidades de certificación raíz de confianza

Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza. El equipo confía en todos los certificados firmados con el certificado en este punto. Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite. Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él. Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario. Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza

1. Abra el complemento del certificado. Para más información, consulte [Visualización de certificados con el complemento MMC](how-to-view-certificates-with-the-mmc-snap-in.md).

2. Abra la carpeta para almacenar el certificado, el **Equipo local** o el **Usuario actual**.

3. Abra la carpeta **Entidades emisoras de certificados raíz de confianza** .

4. Haga clic con el botón secundario en la carpeta **Certificados** y haga clic en **Todas las tareas**, a continuación, haga clic en **Importar**.

5. Siga las instrucciones del asistente en pantalla para importar el archivo RootCA. pfx en el almacén.

## <a name="using-certificates-with-wcf"></a>Uso de certificados con WCF

Una vez que se han preparado los certificados temporales, puede usarlos para desarrollar soluciones WCF que especifiquen los certificados como un tipo de credencial de cliente. Por ejemplo, en la siguiente configuración XML se especifica la seguridad de mensaje y un certificado como tipo de credencial de cliente.

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>Para especificar un certificado como tipo de credencial de cliente

1. En el archivo de configuración de un servicio, use el código XML siguiente para establecer el modo de seguridad en mensaje y el tipo de credencial de cliente en certificado.

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

2. En el archivo de configuración de un cliente, use el código XML siguiente para especificar que el certificado se encuentra en el almacén del usuario y que se puede encontrar buscando el valor "CohoWinery" en el campo SubjectName.

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

Para obtener más información sobre el uso de certificados en WCF, consulte [Working with Certificates](working-with-certificates.md).

## <a name="net-framework-security"></a>seguridad en .NET Framework

Asegúrese de eliminar cualquier los certificados temporales de entidad emisora raíz de las carpetas **Entidades emisoras de certificados raíz de confianza** y **Personal** haciendo clic con el botón secundario en el certificado y, a continuación, haciendo clic en **Eliminar**.

## <a name="see-also"></a>Consulte también

- [Trabajar con certificados](working-with-certificates.md)
- [Procedimiento para ver certificados con el complemento de MMC](how-to-view-certificates-with-the-mmc-snap-in.md)
- [Protección de servicios y clientes](securing-services-and-clients.md)
