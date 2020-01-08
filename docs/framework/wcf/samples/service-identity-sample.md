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
# <a name="service-identity-sample"></a><span data-ttu-id="81658-102">Ejemplo de identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="81658-102">Service Identity Sample</span></span>
<span data-ttu-id="81658-103">Este ejemplo de identidad de servicio muestra cómo establecer la identidad para un servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="81658-104">En el momento del diseño, un cliente puede recuperar la identidad mediante los metadatos del servicio y, en el tiempo de ejecución, el cliente puede autenticar la identidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="81658-105">El concepto de identidad del servicio es permitir a un cliente autenticar un servicio antes de llamar a cualquiera de sus operaciones, protegiendo por lo tanto al cliente de llamadas no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="81658-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="81658-106">En una conexión segura, el servicio autentica también las credenciales de un cliente antes de permitirle acceso, pero éste no es el objetivo de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81658-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="81658-107">Vea los ejemplos de [cliente](../../../../docs/framework/wcf/samples/client.md) que muestran la autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="81658-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="81658-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="81658-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="81658-109">Este ejemplo ilustra las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="81658-109">This sample illustrates the following features:</span></span>

- <span data-ttu-id="81658-110">Cómo establecer los tipos diferentes de identidad en puntos de conexión diferentes para un servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="81658-111">Cada tipo de identidad tiene funciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="81658-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="81658-112">El tipo de identidad para utilizar depende del tipo de credenciales de seguridad utilizado en el enlace del extremo.</span><span class="sxs-lookup"><span data-stu-id="81658-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>

- <span data-ttu-id="81658-113">La identidad se puede establecer mediante declaración en configuración o de forma imperativa en el código.</span><span class="sxs-lookup"><span data-stu-id="81658-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="81658-114">Normalmente para el cliente y el servicio debería utilizar la configuración para establecer la identidad.</span><span class="sxs-lookup"><span data-stu-id="81658-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>

- <span data-ttu-id="81658-115">Cómo definir una identidad personalizada en el cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="81658-116">Normalmente, una identidad personalizada es una personalización de un tipo existente de identidad que permite al cliente examinar otra información de notificación proporcionada en las credenciales del servicio para tomar decisiones de autorización antes de llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81658-117">Este ejemplo comprueba la identidad de un certificado concreto denominado identity.com y la clave RSA contenida dentro de este certificado.</span><span class="sxs-lookup"><span data-stu-id="81658-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="81658-118">Al utilizar los tipos de identidad del certificado y RSA en la configuración en el cliente, una manera fácil de obtener estos valores es inspeccionar WSDL para el servicio donde se serializan estos valores.</span><span class="sxs-lookup"><span data-stu-id="81658-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>

 <span data-ttu-id="81658-119">El código de ejemplo siguiente muestra cómo configurar la identidad de un punto de conexión de servicio con el Servidor de nombres de dominio (DNS) de un certificado utilizando WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="81658-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 <span data-ttu-id="81658-120">La identidad también se puede especificar en la configuración en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="81658-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="81658-121">El ejemplo siguiente muestra cómo establecer la identidad de UPN (Nombre principal del usuario) para un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>

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

 <span data-ttu-id="81658-122">Se puede establecer una identidad personalizada derivando desde las clases <xref:System.ServiceModel.EndpointIdentity> y <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="81658-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="81658-123">De manera conceptual, se puede considerar la clase <xref:System.ServiceModel.Security.IdentityVerifier> para que sea el cliente equivalente de la clase `AuthorizationManager` del servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="81658-124">El ejemplo de código siguiente muestra una implementación de `OrgEndpointIdentity`, que almacena un nombre de la organización para que coincida con el nombre del asunto del certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="81658-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="81658-125">La comprobación de la autorización para el nombre de la organización se produce en el método `CheckAccess` en la clase `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="81658-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>

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

 <span data-ttu-id="81658-126">Este ejemplo utiliza un certificado llamado identity.com que se encuentra en la carpeta de solución de identidad específica del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="81658-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="81658-127">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="81658-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="81658-128">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="81658-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="81658-129">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="81658-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="81658-130">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="81658-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="81658-131">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="81658-131">To run the sample on the same computer</span></span>

1. <span data-ttu-id="81658-132">En [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o Windows Vista, importe el archivo de certificado Identity. pfx en la carpeta identidad de la solución en el almacén de certificados LocalMachine/My (personal) mediante la herramienta de complemento MMC.</span><span class="sxs-lookup"><span data-stu-id="81658-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or Windows Vista, import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="81658-133">Este archivo está protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="81658-133">This file is password protected.</span></span> <span data-ttu-id="81658-134">Durante la importación se pide una contraseña.</span><span class="sxs-lookup"><span data-stu-id="81658-134">During the import you are asked for a password.</span></span> <span data-ttu-id="81658-135">Escriba `xyz` en el cuadro contraseña.</span><span class="sxs-lookup"><span data-stu-id="81658-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="81658-136">Para obtener más información, consulte el tema [Cómo: ver certificados con el complemento MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) .</span><span class="sxs-lookup"><span data-stu-id="81658-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="81658-137">Una vez hecho esto, ejecute setup. bat en un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador, que copia este certificado en el almacén CurrentUser/Trusted People para su uso en el cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-137">Once this is done, run Setup.bat in a Developer Command Prompt for Visual Studio with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>

2. <span data-ttu-id="81658-138">En Windows Server 2003, ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="81658-138">On Windows Server 2003, run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt with administrator privileges.</span></span> <span data-ttu-id="81658-139">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81658-139">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81658-140">El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="81658-140">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="81658-141">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="81658-141">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="81658-142">Asegúrese de que quita los certificados ejecutando Cleanup.bat cuando haya terminado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81658-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="81658-143">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="81658-143">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="81658-144">Inicie Service.exe desde el directorio \service\bin.</span><span class="sxs-lookup"><span data-stu-id="81658-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="81658-145">Asegúrese de que el servicio indica que está listo y muestra un mensaje que le pide que presione \<entrar > para finalizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4. <span data-ttu-id="81658-146">Inicie Client.exe desde el directorio \client\bin o presionando F5 en Visual Studio para compilar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="81658-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="81658-147">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-147">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="81658-148">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="81658-148">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="81658-149">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="81658-149">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="81658-150">Antes de compilar la parte del cliente del ejemplo, asegúrese de cambiar el valor para la dirección de extremo del servicio en el archivo Client.cs en el método `CallServiceCustomClientIdentity`.</span><span class="sxs-lookup"><span data-stu-id="81658-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="81658-151">Después, compile el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81658-151">Then build the sample.</span></span>  
  
2. <span data-ttu-id="81658-152">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-152">Create a directory on the service computer.</span></span>  
  
3. <span data-ttu-id="81658-153">Copie los archivos de programa del servicio desde service\bin en el directorio del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="81658-154">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4. <span data-ttu-id="81658-155">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5. <span data-ttu-id="81658-156">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="81658-157">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6. <span data-ttu-id="81658-158">En el servicio, ejecute `setup.bat service` en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="81658-158">On the service, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="81658-159">Al ejecutar `setup.bat` con el argumento `service`, se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="81658-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7. <span data-ttu-id="81658-160">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="81658-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="81658-161">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="81658-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="81658-162">Hay varias instancias que deben cambiarse.</span><span class="sxs-lookup"><span data-stu-id="81658-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="81658-163">En el cliente, ejecute ImportServiceCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="81658-163">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="81658-164">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="81658-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="81658-165">En el equipo del servicio, inicie el archivo Service.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="81658-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="81658-166">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="81658-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="81658-167">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="81658-167">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="81658-168">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="81658-168">To clean up after the sample</span></span>  
  
- <span data-ttu-id="81658-169">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81658-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="81658-170">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="81658-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="81658-171">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="81658-171">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="81658-172">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="81658-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
