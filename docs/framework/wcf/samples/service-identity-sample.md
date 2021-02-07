---
description: 'Más información acerca de: ejemplo de identidad de servicio'
title: Ejemplo de identidad de servicio
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: 5fa3dc9454d816655d3d3f2af165df19e1c65e15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703528"
---
# <a name="service-identity-sample"></a><span data-ttu-id="15aa8-103">Ejemplo de identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="15aa8-103">Service Identity Sample</span></span>

<span data-ttu-id="15aa8-104">Este ejemplo de identidad de servicio muestra cómo establecer la identidad para un servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-104">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="15aa8-105">En el momento del diseño, un cliente puede recuperar la identidad mediante los metadatos del servicio y, en el tiempo de ejecución, el cliente puede autenticar la identidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-105">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="15aa8-106">El concepto de identidad del servicio es permitir a un cliente autenticar un servicio antes de llamar a cualquiera de sus operaciones, protegiendo por lo tanto al cliente de llamadas no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="15aa8-106">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="15aa8-107">En una conexión segura, el servicio autentica también las credenciales de un cliente antes de permitirle acceso, pero éste no es el objetivo de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-107">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="15aa8-108">Vea los ejemplos de [cliente](client.md) que muestran la autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="15aa8-108">See the samples in [Client](client.md) that show server authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="15aa8-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="15aa8-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="15aa8-110">Este ejemplo ilustra las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="15aa8-110">This sample illustrates the following features:</span></span>

- <span data-ttu-id="15aa8-111">Cómo establecer los tipos diferentes de identidad en puntos de conexión diferentes para un servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-111">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="15aa8-112">Cada tipo de identidad tiene funciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="15aa8-112">Each type of identity has different capabilities.</span></span> <span data-ttu-id="15aa8-113">El tipo de identidad para utilizar depende del tipo de credenciales de seguridad utilizado en el enlace del extremo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-113">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>

- <span data-ttu-id="15aa8-114">La identidad se puede establecer mediante declaración en configuración o de forma imperativa en el código.</span><span class="sxs-lookup"><span data-stu-id="15aa8-114">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="15aa8-115">Normalmente para el cliente y el servicio debería utilizar la configuración para establecer la identidad.</span><span class="sxs-lookup"><span data-stu-id="15aa8-115">Typically for both the client and the service you should use configuration to set the identity.</span></span>

- <span data-ttu-id="15aa8-116">Cómo definir una identidad personalizada en el cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-116">How to set a custom identity on the client.</span></span> <span data-ttu-id="15aa8-117">Normalmente, una identidad personalizada es una personalización de un tipo existente de identidad que permite al cliente examinar otra información de notificación proporcionada en las credenciales del servicio para tomar decisiones de autorización antes de llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-117">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15aa8-118">Este ejemplo comprueba la identidad de un certificado concreto denominado identity.com y la clave RSA contenida dentro de este certificado.</span><span class="sxs-lookup"><span data-stu-id="15aa8-118">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="15aa8-119">Al utilizar los tipos de identidad del certificado y RSA en la configuración en el cliente, una manera fácil de obtener estos valores es inspeccionar WSDL para el servicio donde se serializan estos valores.</span><span class="sxs-lookup"><span data-stu-id="15aa8-119">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>

 <span data-ttu-id="15aa8-120">El código de ejemplo siguiente muestra cómo configurar la identidad de un punto de conexión de servicio con el Servidor de nombres de dominio (DNS) de un certificado utilizando WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="15aa8-120">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 <span data-ttu-id="15aa8-121">La identidad también se puede especificar en la configuración en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="15aa8-121">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="15aa8-122">El ejemplo siguiente muestra cómo establecer la identidad de UPN (Nombre principal del usuario) para un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-122">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>

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

 <span data-ttu-id="15aa8-123">Se puede establecer una identidad personalizada derivando desde las clases <xref:System.ServiceModel.EndpointIdentity> y <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="15aa8-123">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="15aa8-124">De manera conceptual, se puede considerar la clase <xref:System.ServiceModel.Security.IdentityVerifier> para que sea el cliente equivalente de la clase `AuthorizationManager` del servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-124">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="15aa8-125">El ejemplo de código siguiente muestra una implementación de `OrgEndpointIdentity`, que almacena un nombre de la organización para que coincida con el nombre del asunto del certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="15aa8-125">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="15aa8-126">La comprobación de la autorización para el nombre de la organización se produce en el método `CheckAccess` en la clase `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="15aa8-126">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>

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

 <span data-ttu-id="15aa8-127">Este ejemplo utiliza un certificado llamado identity.com que se encuentra en la carpeta de solución de identidad específica del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="15aa8-127">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="15aa8-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="15aa8-128">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="15aa8-129">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15aa8-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="15aa8-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15aa8-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="15aa8-131">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15aa8-131">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="15aa8-132">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="15aa8-132">To run the sample on the same computer</span></span>

1. <span data-ttu-id="15aa8-133">En Windows XP o Windows Vista, importe el archivo de certificado Identity. pfx en la carpeta identidad de la solución en el almacén de certificados LocalMachine/My (personal) mediante la herramienta de complemento MMC.</span><span class="sxs-lookup"><span data-stu-id="15aa8-133">On Windows XP or Windows Vista, import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="15aa8-134">Este archivo está protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="15aa8-134">This file is password protected.</span></span> <span data-ttu-id="15aa8-135">Durante la importación se pide una contraseña.</span><span class="sxs-lookup"><span data-stu-id="15aa8-135">During the import you are asked for a password.</span></span> <span data-ttu-id="15aa8-136">Escriba `xyz` en el cuadro contraseña.</span><span class="sxs-lookup"><span data-stu-id="15aa8-136">Type `xyz` into the password box.</span></span> <span data-ttu-id="15aa8-137">Para obtener más información, consulte el tema [Cómo: ver certificados con el complemento MMC](../feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) .</span><span class="sxs-lookup"><span data-stu-id="15aa8-137">For more information, see the [How to: View Certificates with the MMC Snap-in](../feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="15aa8-138">Una vez hecho esto, ejecute Setup.bat en un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador, que copia este certificado en el almacén CurrentUser/Trusted People para su uso en el cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-138">Once this is done, run Setup.bat in a Developer Command Prompt for Visual Studio with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>

2. <span data-ttu-id="15aa8-139">En Windows Server 2003, ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="15aa8-139">On Windows Server 2003, run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt with administrator privileges.</span></span> <span data-ttu-id="15aa8-140">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-140">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15aa8-141">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="15aa8-141">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="15aa8-142">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="15aa8-142">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="15aa8-143">Asegúrese de que quita los certificados ejecutando Cleanup.bat cuando haya terminado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-143">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="15aa8-144">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="15aa8-144">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="15aa8-145">Inicie Service.exe desde el directorio \service\bin.</span><span class="sxs-lookup"><span data-stu-id="15aa8-145">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="15aa8-146">Asegúrese de que el servicio indica que está listo y muestra un mensaje que le pide que presione \<Enter> para finalizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-146">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4. <span data-ttu-id="15aa8-147">Inicie Client.exe desde el directorio \client\bin o presionando F5 en Visual Studio para compilar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="15aa8-147">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="15aa8-148">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-148">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="15aa8-149">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="15aa8-149">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="15aa8-150">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="15aa8-150">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="15aa8-151">Antes de compilar la parte del cliente del ejemplo, asegúrese de cambiar el valor para la dirección de extremo del servicio en el archivo Client.cs en el método `CallServiceCustomClientIdentity`.</span><span class="sxs-lookup"><span data-stu-id="15aa8-151">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="15aa8-152">Después, compile el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-152">Then build the sample.</span></span>  
  
2. <span data-ttu-id="15aa8-153">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-153">Create a directory on the service computer.</span></span>  
  
3. <span data-ttu-id="15aa8-154">Copie los archivos de programa del servicio desde service\bin en el directorio del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-154">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="15aa8-155">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-155">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4. <span data-ttu-id="15aa8-156">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-156">Create a directory on the client computer for the client binaries.</span></span>  
  
5. <span data-ttu-id="15aa8-157">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-157">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="15aa8-158">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-158">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6. <span data-ttu-id="15aa8-159">En el servicio, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="15aa8-159">On the service, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="15aa8-160">`setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="15aa8-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7. <span data-ttu-id="15aa8-161">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="15aa8-161">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="15aa8-162">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="15aa8-162">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="15aa8-163">Hay varias instancias que deben cambiarse.</span><span class="sxs-lookup"><span data-stu-id="15aa8-163">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="15aa8-164">En el cliente, ejecute ImportServiceCert.bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="15aa8-164">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="15aa8-165">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="15aa8-165">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="15aa8-166">En el equipo del servicio, inicie el archivo Service.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="15aa8-166">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="15aa8-167">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="15aa8-167">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="15aa8-168">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="15aa8-168">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="15aa8-169">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="15aa8-169">To clean up after the sample</span></span>  
  
- <span data-ttu-id="15aa8-170">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15aa8-170">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="15aa8-171">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="15aa8-171">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="15aa8-172">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="15aa8-172">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="15aa8-173">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="15aa8-173">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
