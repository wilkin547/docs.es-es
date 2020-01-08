---
title: Ejemplo de identidad de servicio
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: 375246127b6b39440360f48fc7b24bd0388a35e5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347921"
---
# <a name="service-identity-sample"></a>Ejemplo de identidad de servicio
Este ejemplo de identidad de servicio muestra cómo establecer la identidad para un servicio. En el momento del diseño, un cliente puede recuperar la identidad mediante los metadatos del servicio y, en el tiempo de ejecución, el cliente puede autenticar la identidad del servicio. El concepto de identidad del servicio es permitir a un cliente autenticar un servicio antes de llamar a cualquiera de sus operaciones, protegiendo por lo tanto al cliente de llamadas no autenticadas. En una conexión segura, el servicio autentica también las credenciales de un cliente antes de permitirle acceso, pero éste no es el objetivo de este ejemplo. Vea los ejemplos de [cliente](../../../../docs/framework/wcf/samples/client.md) que muestran la autenticación de servidor.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

 Este ejemplo ilustra las siguientes características:

- Cómo establecer los tipos diferentes de identidad en puntos de conexión diferentes para un servicio. Cada tipo de identidad tiene funciones diferentes. El tipo de identidad para utilizar depende del tipo de credenciales de seguridad utilizado en el enlace del extremo.

- La identidad se puede establecer mediante declaración en configuración o de forma imperativa en el código. Normalmente para el cliente y el servicio debería utilizar la configuración para establecer la identidad.

- Cómo definir una identidad personalizada en el cliente. Normalmente, una identidad personalizada es una personalización de un tipo existente de identidad que permite al cliente examinar otra información de notificación proporcionada en las credenciales del servicio para tomar decisiones de autorización antes de llamar al servicio.

    > [!NOTE]
    > Este ejemplo comprueba la identidad de un certificado concreto denominado identity.com y la clave RSA contenida dentro de este certificado. Al utilizar los tipos de identidad del certificado y RSA en la configuración en el cliente, una manera fácil de obtener estos valores es inspeccionar WSDL para el servicio donde se serializan estos valores.

 El código de ejemplo siguiente muestra cómo configurar la identidad de un punto de conexión de servicio con el Servidor de nombres de dominio (DNS) de un certificado utilizando WSHttpBinding.

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 La identidad también se puede especificar en la configuración en el archivo App.config. El ejemplo siguiente muestra cómo establecer la identidad de UPN (Nombre principal del usuario) para un punto de conexión de servicio.

```xml
<endpoint address="upnidentity"
        behaviorConfiguration=""
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_Windows"
        name="WSHttpBinding_ICalculator_Windows"
        contract="Microsoft.ServiceModel.Samples.ICalculator">
  <!-- Set the UPN identity for this endpoint -->
  <identity>
      <userPrincipalName value="host\myservice.com" />
  </identity >
</endpoint>
```

 Se puede establecer una identidad personalizada derivando desde las clases <xref:System.ServiceModel.EndpointIdentity> y <xref:System.ServiceModel.Security.IdentityVerifier>. De manera conceptual, se puede considerar la clase <xref:System.ServiceModel.Security.IdentityVerifier> para que sea el cliente equivalente de la clase `AuthorizationManager` del servicio. El ejemplo de código siguiente muestra una implementación de `OrgEndpointIdentity`, que almacena un nombre de la organización para que coincida con el nombre del asunto del certificado del servidor. La comprobación de la autorización para el nombre de la organización se produce en el método `CheckAccess` en la clase `CustomIdentityVerifier`.

```csharp
// This custom EndpointIdentity stores an organization name
public class OrgEndpointIdentity : EndpointIdentity
{
    private string orgClaim;
    public OrgEndpointIdentity(string orgName)
    {
        orgClaim = orgName;
    }
    public string OrganizationClaim
    {
        get { return orgClaim; }
        set { orgClaim = value; }
    }
}

//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to
//check that X.509 certificate's distinguished name claim contains
//the organization name e.g. the string value "O=Contoso"
class CustomIdentityVerifier : IdentityVerifier
{
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)
    {
        bool returnvalue = false;
        foreach (ClaimSet claimset in authContext.ClaimSets)
        {
            foreach (Claim claim in claimset)
            {
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")
                {
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))
                    {
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);
                        Console.WriteLine("Right: {0}", claim.Right);
                        Console.WriteLine("Resource: {0}",claim.Resource);
                        Console.WriteLine();
                        returnvalue = true;
                    }
                }
            }
        }
        return returnvalue;
    }
}
```

 Este ejemplo utiliza un certificado llamado identity.com que se encuentra en la carpeta de solución de identidad específica del lenguaje.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. En [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o Windows Vista, importe el archivo de certificado Identity. pfx en la carpeta identidad de la solución en el almacén de certificados LocalMachine/My (personal) mediante la herramienta de complemento MMC. Este archivo está protegido con contraseña. Durante la importación se pide una contraseña. Escriba `xyz` en el cuadro contraseña. Para obtener más información, consulte el tema [Cómo: ver certificados con el complemento MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) . Una vez hecho esto, ejecute setup. bat en un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador, que copia este certificado en el almacén CurrentUser/Trusted People para su uso en el cliente.

2. En Windows Server 2003, ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat. Asegúrese de que quita los certificados ejecutando Cleanup.bat cuando haya terminado con el ejemplo. Otros ejemplos de seguridad usan los mismos certificados.  
  
3. Inicie Service.exe desde el directorio \service\bin. Asegúrese de que el servicio indica que está listo y muestra un mensaje que le pide que presione \<entrar > para finalizar el servicio.  
  
4. Inicie Client.exe desde el directorio \client\bin o presionando F5 en Visual Studio para compilar y ejecutar. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
5. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Antes de compilar la parte del cliente del ejemplo, asegúrese de cambiar el valor para la dirección de extremo del servicio en el archivo Client.cs en el método `CallServiceCustomClientIdentity`. Después, compile el ejemplo.  
  
2. Cree un directorio en el equipo del servicio.  
  
3. Copie los archivos de programa del servicio desde service\bin en el directorio del equipo de servicio. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
4. Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
5. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
6. En el servicio, ejecute `setup.bat service` en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Al ejecutar `setup.bat` con el argumento `service`, se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.  
  
7. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio. Hay varias instancias que deben cambiarse.  
  
9. En el cliente, ejecute ImportServiceCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
10. En el equipo del servicio, inicie el archivo Service.exe desde el símbolo del sistema.  
  
11. En el equipo cliente, inicie Client.exe desde un símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
    > [!NOTE]
    > Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.
