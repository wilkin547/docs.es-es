---
description: 'Más información acerca de: pertenencia y proveedor de roles'
title: Proveedor de pertenencia y roles
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: ec7c59729241f811b485195eb7e2f292fb604e03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732389"
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="eb3cf-103">Proveedor de pertenencia y roles</span><span class="sxs-lookup"><span data-stu-id="eb3cf-103">Membership and Role Provider</span></span>

<span data-ttu-id="eb3cf-104">El ejemplo de pertenencia y del proveedor de roles muestra cómo un servicio puede usar la pertenencia a ASP.NET y los proveedores de roles para autenticar y autorizar a los clientes.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-104">The Membership and Role Provider sample demonstrates how a service can use the ASP.NET membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="eb3cf-105">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb3cf-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="eb3cf-107">Este ejemplo demuestra cómo:</span><span class="sxs-lookup"><span data-stu-id="eb3cf-107">The sample demonstrates how:</span></span>  
  
- <span data-ttu-id="eb3cf-108">Un cliente se puede autenticar utilizando la combinación de nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-108">A client can authenticate by using the username-password combination.</span></span>  
  
- <span data-ttu-id="eb3cf-109">El servidor puede validar las credenciales del cliente con el proveedor de pertenencia de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-109">The server can validate the client credentials against the ASP.NET membership provider.</span></span>  
  
- <span data-ttu-id="eb3cf-110">El servidor se puede autenticar utilizando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-110">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
- <span data-ttu-id="eb3cf-111">El servidor puede asignar el cliente autenticado a un rol mediante el proveedor de roles ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-111">The server can map the authenticated client to a role by using the ASP.NET role provider.</span></span>  
  
- <span data-ttu-id="eb3cf-112">El servidor puede utilizar `PrincipalPermissionAttribute` para controlar el acceso a ciertos métodos expuestos por el servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-112">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="eb3cf-113">Los proveedores de roles y pertenencia se configuran para utilizar un almacén respaldado por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-113">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="eb3cf-114">En el archivo de configuración del servicio se especifica una cadena de conexión y varias opciones.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-114">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="eb3cf-115">Al proveedor de pertenencia se le da el nombre `SqlMembershipProvider` y al proveedor de roles se le da el nombre `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-115">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add
        name="SqlMembershipProvider"
        type="System.Web.Security.SqlMembershipProvider"
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="eb3cf-116">El servicio expone un extremo único para comunicarse con el servicio, que se define utilizando el archivo de configuración Web.config.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-116">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="eb3cf-117">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="eb3cf-118">El enlace se configura con un `wsHttpBinding` estándar, que usa la autenticación de Windows de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-118">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="eb3cf-119">Este ejemplo establece el `wsHttpBinding` estándar para utilizar la autenticación mediante el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-119">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="eb3cf-120">El comportamiento especifica que se va a usar el certificado de servidor para la autenticación del servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-120">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="eb3cf-121">El certificado de servidor debe contener el mismo valor para el `SubjectName` que el `findValue` atributo del [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-121">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="eb3cf-122">Además, el comportamiento especifica que el proveedor de pertenencia de ASP.NET realiza la autenticación de los pares de nombre de usuario y contraseña mediante el proveedor de roles ASP.NET especificando los nombres definidos para los dos proveedores.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-122">In addition the behavior specifies that authentication of username-password pairs is performed by the ASP.NET membership provider and role mapping is performed by the ASP.NET role provider by specifying the names defined for the two providers.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"
                              storeName ="My"
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="eb3cf-123">Al ejecutar el ejemplo, el cliente llama a las distintas operaciones de servicio en tres cuentas de usuario diferentes: Alice, Bob y Charlie.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-123">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="eb3cf-124">Las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-124">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="eb3cf-125">Las cuatro llamadas que se efectúan como el usuario "Alice" deberían poder realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-125">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="eb3cf-126">El usuario "Bob" debería obtener un error de acceso denegado al intentar llamar al método Divide.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-126">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="eb3cf-127">El usuario "Charlie" debería obtener un error de acceso denegado al intentar llamar al método Multiply.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-127">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="eb3cf-128">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-128">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eb3cf-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb3cf-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="eb3cf-130">Para compilar la edición de C# o Visual Basic .NET de la solución, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="eb3cf-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
2. <span data-ttu-id="eb3cf-131">Asegúrese de que ha configurado la [base de datos de servicios de aplicación de ASP.net](https://go.microsoft.com/fwlink/?LinkId=94997).</span><span class="sxs-lookup"><span data-stu-id="eb3cf-131">Ensure that you have configured the [ASP.NET Application Services Database](https://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="eb3cf-132">Si está ejecutando SQL Server Express Edition, su nombre de servidor es .\SQLEXPRESS.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-132">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="eb3cf-133">Este servidor se debe usar al configurar la base de datos de Servicios de aplicación de ASP.NET, así como en la cadena de conexión de Web.config.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-133">This server should be used when configuring the ASP.NET Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="eb3cf-134">La cuenta de proceso de trabajo de ASP.NET debe tener permisos en la base de datos que se crea en este paso.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-134">The ASP.NET worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="eb3cf-135">Use la utilidad sqlcmd o SQL Server Management Studio para ello.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-135">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3. <span data-ttu-id="eb3cf-136">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-136">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="eb3cf-137">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="eb3cf-137">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="eb3cf-138">Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentra Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-138">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="eb3cf-139">Ejecute Setup.bat desde la carpeta de instalación de ejemplo en un Símbolo del sistema para desarrolladores para que Visual Studio se ejecute con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-139">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="eb3cf-140">De esta forma se instalan los certificados de servicio necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-140">This installs the service certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="eb3cf-141">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-141">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="eb3cf-142">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-142">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="eb3cf-143">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="eb3cf-143">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="eb3cf-144">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="eb3cf-144">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="eb3cf-145">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-145">Create a directory on the service computer.</span></span> <span data-ttu-id="eb3cf-146">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="eb3cf-146">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="eb3cf-147">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-147">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="eb3cf-148">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-148">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="eb3cf-149">Copie también los archivos Setup.bat, GetComputerName.vbs y Cleanup.bat en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-149">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="eb3cf-150">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-150">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="eb3cf-151">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-151">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="eb3cf-152">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-152">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="eb3cf-153">En el servidor, abra una Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute `setup.bat service` .</span><span class="sxs-lookup"><span data-stu-id="eb3cf-153">On the server, open a Developer Command Prompt for Visual Studio with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="eb3cf-154">`setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-154">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="eb3cf-155">Edite Web.config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-155">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="eb3cf-156">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-156">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="eb3cf-157">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-157">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="eb3cf-158">En el cliente, abra una Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-158">On the client, open a Developer Command Prompt for Visual Studio with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="eb3cf-159">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-159">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="eb3cf-160">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-160">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="eb3cf-161">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="eb3cf-161">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="eb3cf-162">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb3cf-162">To clean up after the sample</span></span>  
  
- <span data-ttu-id="eb3cf-163">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-163">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb3cf-164">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-164">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="eb3cf-165">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-165">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="eb3cf-166">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-166">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="eb3cf-167">Archivo de instalación por lotes</span><span class="sxs-lookup"><span data-stu-id="eb3cf-167">The Setup Batch File</span></span>  

 <span data-ttu-id="eb3cf-168">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-168">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="eb3cf-169">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-169">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="eb3cf-170">A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-170">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
- <span data-ttu-id="eb3cf-171">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-171">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="eb3cf-172">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-172">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="eb3cf-173">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-173">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="eb3cf-174">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-174">Change this variable to specify your own server name.</span></span> <span data-ttu-id="eb3cf-175">Este archivo por lotes tiene como valor predeterminado el host local.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-175">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="eb3cf-176">El certificado se almacena en el almacén My (Personal), en la ubicación de almacenamiento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-176">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```console
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="eb3cf-177">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-177">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="eb3cf-178">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-178">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="eb3cf-179">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-179">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="eb3cf-180">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3cf-180">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```
