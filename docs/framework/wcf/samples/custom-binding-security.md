---
description: 'Más información sobre: seguridad de enlace personalizado'
title: Seguridad de enlace personalizado
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: f0ed4b40fe4e0869f34a4f6016123dc9f0a57f45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732636"
---
# <a name="custom-binding-security"></a><span data-ttu-id="1948b-103">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="1948b-103">Custom Binding Security</span></span>

<span data-ttu-id="1948b-104">Este ejemplo muestra cómo configurar la seguridad mediante un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="1948b-104">This sample demonstrates how to configure security by using a custom binding.</span></span> <span data-ttu-id="1948b-105">Muestra cómo utilizar un enlace personalizado para habilitar la seguridad de nivel de mensaje junto con un transporte seguro.</span><span class="sxs-lookup"><span data-stu-id="1948b-105">It shows how to use a custom binding to enable message-level security together with a secure transport.</span></span> <span data-ttu-id="1948b-106">Esto es útil cuando se exige un transporte seguro que transmita los mensajes entre el cliente y servicio y simultáneamente los mensajes deben ser seguros en el nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1948b-106">This is useful when a secure transport is required to transmit the messages between client and service and simultaneously the messages must be secure on the message level.</span></span> <span data-ttu-id="1948b-107">Los enlaces proporcionados por el sistema no admiten esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1948b-107">This configuration is not supported by system-provided bindings.</span></span>

<span data-ttu-id="1948b-108">Este ejemplo está compuesto por un programa de consola de cliente (EXE) y un programa de consola de servicio (EXE).</span><span class="sxs-lookup"><span data-stu-id="1948b-108">This sample consists of a client console program (EXE) and a service console program (EXE).</span></span> <span data-ttu-id="1948b-109">El servicio implementa un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="1948b-109">The service implements a duplex contract.</span></span> <span data-ttu-id="1948b-110">La interfaz `ICalculatorDuplex`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato.</span><span class="sxs-lookup"><span data-stu-id="1948b-110">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="1948b-111">La interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones de matemática, calculando un resultado en ejecución sobre una sesión.</span><span class="sxs-lookup"><span data-stu-id="1948b-111">The `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over a session.</span></span> <span data-ttu-id="1948b-112">Independientemente, el servicio puede devolver resultados en la interfaz `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="1948b-112">Independently, the service may return results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="1948b-113">Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-113">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span> <span data-ttu-id="1948b-114">Se define un enlace personalizado que admite la comunicación dúplex y es seguro.</span><span class="sxs-lookup"><span data-stu-id="1948b-114">A custom binding is defined that supports duplex communication and is secure.</span></span>

> [!NOTE]
> <span data-ttu-id="1948b-115">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="1948b-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="1948b-116">La configuración del servicio define un enlace personalizado que admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1948b-116">The service configuration defines a custom binding that supports the following:</span></span>

- <span data-ttu-id="1948b-117">Comunicación TCP protegida mediante el protocolo TLS/SSL.</span><span class="sxs-lookup"><span data-stu-id="1948b-117">TCP communication protected by using the TLS/SSL protocol.</span></span>

- <span data-ttu-id="1948b-118">Seguridad de mensaje de Windows.</span><span class="sxs-lookup"><span data-stu-id="1948b-118">Windows message security.</span></span>

<span data-ttu-id="1948b-119">La configuración de enlace personalizado permite el transporte seguro, habilitando simultáneamente la seguridad de nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1948b-119">The custom binding configuration enables secure transport by simultaneously enabling the message-level security.</span></span> <span data-ttu-id="1948b-120">El orden de los elementos de enlace es importante en la definición de un enlace personalizado, ya que cada uno representa una capa en la pila del canal (vea [enlaces personalizados](../extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="1948b-120">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span> <span data-ttu-id="1948b-121">El enlace personalizado se define en los archivos de configuración de cliente y servicio, como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1948b-121">The custom binding is defined in the service and client configuration files, as shown in the following sample configuration.</span></span>

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

<span data-ttu-id="1948b-122">El enlace personalizado utiliza un certificado de servicio para autenticar el servicio en el nivel de transporte y proteger los mensajes durante la transmisión entre el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-122">The custom binding uses a service certificate to authenticate the service on the transport level and to protect the messages during the transmission between client and service.</span></span> <span data-ttu-id="1948b-123">Esto lo lleva a cabo el elemento de enlace `sslStreamSecurity`.</span><span class="sxs-lookup"><span data-stu-id="1948b-123">This is accomplished by the `sslStreamSecurity` binding element.</span></span> <span data-ttu-id="1948b-124">El certificado del servicio se configura utilizando un comportamiento del servicio como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1948b-124">The service's certificate is configured using a service behavior as shown in the following sample configuration.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="1948b-125">Además, el enlace personalizado utiliza seguridad de mensajes con tipo de credencial de Windows; éste es el tipo de credencial predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1948b-125">Additionally, the custom binding uses message security with Windows credential type - this is the default credential type.</span></span> <span data-ttu-id="1948b-126">Esto lo lleva a cabo el elemento de enlace `security`.</span><span class="sxs-lookup"><span data-stu-id="1948b-126">This is accomplished by the `security` binding element.</span></span> <span data-ttu-id="1948b-127">Cliente y servicio se autentican utilizando la seguridad de nivel de mensaje si el mecanismo de autenticación Kerberos está disponible.</span><span class="sxs-lookup"><span data-stu-id="1948b-127">Both client and service are authenticated using message-level security if the Kerberos authentication mechanism is available.</span></span> <span data-ttu-id="1948b-128">Esto sucede si el ejemplo se ejecuta en el entorno de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1948b-128">This happens if the sample is run in the Active Directory environment.</span></span> <span data-ttu-id="1948b-129">Si el mecanismo de autenticación Kerberos no está disponible, se utiliza la autenticación NTLM.</span><span class="sxs-lookup"><span data-stu-id="1948b-129">If the Kerberos authentication mechanism is not available, NTLM authentication is used.</span></span> <span data-ttu-id="1948b-130">NTLM autentica el cliente para el servicio pero no autentica el servicio para el cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-130">NTLM authenticates the client to the service but does not authenticate the service to the client.</span></span> <span data-ttu-id="1948b-131">El `security` elemento de enlace se configura para utilizar `SecureConversation` `authenticationType` , lo que da lugar a la creación de una sesión de seguridad tanto en el cliente como en el servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-131">The `security` binding element is configured to use `SecureConversation` `authenticationType`, which results in the creation of a security session on both the client and the service.</span></span> <span data-ttu-id="1948b-132">Esto se exige para que funcione el contrato del dúplex del servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-132">This is required to enable the service's duplex contract to work.</span></span>

<span data-ttu-id="1948b-133">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-133">When you run the sample, the operation requests and responses are displayed in the client's console window.</span></span> <span data-ttu-id="1948b-134">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-134">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="1948b-135">Al ejecutar el ejemplo, se ven los mensajes devueltos al cliente en la interfaz de devolución de llamada enviada del servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-135">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="1948b-136">Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="1948b-136">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="1948b-137">Presione Entrar para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-137">Press ENTER to shut down the client.</span></span>

<span data-ttu-id="1948b-138">El archivo Setup.bat incluido con este ejemplo permite configurar el cliente y el servidor con los certificados de servicio pertinentes para ejecutar una aplicación hospedada que requiera seguridad basada en certificado.</span><span class="sxs-lookup"><span data-stu-id="1948b-138">The included Setup.bat file enables you to configure the client and server with the relevant service certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="1948b-139">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1948b-139">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="1948b-140">A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes que se aplican en este ejemplo con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="1948b-140">The following provides a brief overview of the different sections of the batch files that apply to this sample so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="1948b-141">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="1948b-141">Creating the server certificate.</span></span>

  <span data-ttu-id="1948b-142">Las líneas siguientes del archivo Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1948b-142">The following lines from the Setup.bat file create the server certificate to be used.</span></span> <span data-ttu-id="1948b-143">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="1948b-143">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="1948b-144">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="1948b-144">Change this variable to specify your own server name.</span></span> <span data-ttu-id="1948b-145">Este archivo por lotes determina como valor predeterminado el nombre del servidor como host local.</span><span class="sxs-lookup"><span data-stu-id="1948b-145">This batch file defaults the server name to localhost.</span></span>

  <span data-ttu-id="1948b-146">El certificado se almacena en el almacén de CurrentUser para los servicios hospedados en web.</span><span class="sxs-lookup"><span data-stu-id="1948b-146">The certificate is stored in the CurrentUser store for the Web-hosted services.</span></span>

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- <span data-ttu-id="1948b-147">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-147">Installing the server certificate into the client's trusted certificate store.</span></span>

  <span data-ttu-id="1948b-148">Las líneas siguientes del archivo Setup.bat copian el certificado de servidor en el almacén de usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-148">The following lines in the Setup.bat file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="1948b-149">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="1948b-149">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="1948b-150">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="1948b-150">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > <span data-ttu-id="1948b-151">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1948b-151">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="1948b-152">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="1948b-152">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="1948b-153">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1948b-153">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1948b-154">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1948b-154">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1948b-155">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1948b-155">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1948b-156">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1948b-156">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="1948b-157">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1948b-157">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1948b-158">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="1948b-158">To run the sample on the same computer</span></span>

1. <span data-ttu-id="1948b-159">Abra un Símbolo del sistema para desarrolladores para la ventana de Visual Studio con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1948b-159">Open a Developer Command Prompt for Visual Studio window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="1948b-160">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1948b-160">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1948b-161">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="1948b-161">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="1948b-162">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="1948b-162">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="1948b-163">Inicie Service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="1948b-163">Launch Service.exe from \service\bin.</span></span>

3. <span data-ttu-id="1948b-164">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="1948b-164">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="1948b-165">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-165">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="1948b-166">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1948b-166">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1948b-167">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="1948b-167">To run the sample across computers</span></span>

1. <span data-ttu-id="1948b-168">En el equipo del servicio:</span><span class="sxs-lookup"><span data-stu-id="1948b-168">On the service computer:</span></span>

    1. <span data-ttu-id="1948b-169">Cree un directorio virtual denominado servicemodelsamples en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-169">Create a virtual directory named servicemodelsamples on the service computer.</span></span>

    2. <span data-ttu-id="1948b-170">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-170">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="1948b-171">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="1948b-171">Ensure that you copy the files in the \bin subdirectory.</span></span>

    3. <span data-ttu-id="1948b-172">Copie los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-172">Copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>

    4. <span data-ttu-id="1948b-173">Ejecute el siguiente comando en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador: `Setup.bat service` .</span><span class="sxs-lookup"><span data-stu-id="1948b-173">Run the following command in a Developer Command Prompt for Visual Studio opened with administrator privileges: `Setup.bat service`.</span></span> <span data-ttu-id="1948b-174">Así se crea el certificado del servicio con un nombre de sujeto que coincide con el nombre del equipo en el que se ejecutó el archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="1948b-174">This creates the service certificate with the subject name matching the name of the computer the batch file was run on.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1948b-175">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1948b-175">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="1948b-176">Requiere que la variable de entorno path señale al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="1948b-176">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="1948b-177">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1948b-177">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

    5. <span data-ttu-id="1948b-178">Cambie en [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) el archivo de Service.exe.config para que refleje el nombre de sujeto del certificado generado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="1948b-178">Change the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) inside the Service.exe.config file to reflect the subject name of the certificate generated in the previous step.</span></span>

    6. <span data-ttu-id="1948b-179">Ejecute Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1948b-179">Run Service.exe from a command prompt.</span></span>

2. <span data-ttu-id="1948b-180">En el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="1948b-180">On the client computer:</span></span>

    1. <span data-ttu-id="1948b-181">Copie los archivos de programa del cliente de la carpeta \client\bin\ al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="1948b-181">Copy the client program files from the \client\bin\ folder to the client computer.</span></span> <span data-ttu-id="1948b-182">Copie también el archivo Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="1948b-182">Also copy the Cleanup.bat file.</span></span>

    2. <span data-ttu-id="1948b-183">Ejecute Cleanup.bat para quitar cualquier certificado antiguo de ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1948b-183">Run Cleanup.bat to remove any old certificates from previous samples.</span></span>

    3. <span data-ttu-id="1948b-184">Exporte el certificado del servicio abriendo un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecutando el siguiente comando en el equipo del servicio (sustituya `%SERVER_NAME%` por el nombre completo del equipo donde se está ejecutando el servicio):</span><span class="sxs-lookup"><span data-stu-id="1948b-184">Export the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the service computer (substitute `%SERVER_NAME%` with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. <span data-ttu-id="1948b-185">Copie % SERVER_NAME%.cer en el equipo cliente (sustituya % SERVER_NAME% con el nombre completo del equipo donde se está ejecutando el servicio).</span><span class="sxs-lookup"><span data-stu-id="1948b-185">Copy %SERVER_NAME%.cer to the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running).</span></span>

    5. <span data-ttu-id="1948b-186">Importe el certificado del servicio abriendo un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecutando el siguiente comando en el equipo cliente (sustituya% SERVER_NAME% por el nombre completo del equipo en el que se está ejecutando el servicio):</span><span class="sxs-lookup"><span data-stu-id="1948b-186">Import the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        <span data-ttu-id="1948b-187">Los pasos c, d y e no son necesarios si el certificado procede de un emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="1948b-187">Steps c, d, and e are not necessary if the certificate is issued by a Trusted Issuer.</span></span>

    6. <span data-ttu-id="1948b-188">Modifique el archivo App.config del cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="1948b-188">Modify the client’s App.config file as follows:</span></span>

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. <span data-ttu-id="1948b-189">Si el servicio se está ejecutando con una cuenta que no es NetworkService o LocalSystem en un entorno de dominio, puede que sea necesario modificar la identidad del extremo de servicio en el archivo App.config del cliente para establecer el UPN o SPN adecuado en función de la cuenta que se utilice para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="1948b-189">If the service is running under an account other than the NetworkService or LocalSystem account in a domain environment, you might need to modify the endpoint identity for the service endpoint inside the client's App.config file to set the appropriate UPN or SPN based on the account that is used to run the service.</span></span> <span data-ttu-id="1948b-190">Para obtener más información acerca de la identidad del punto de conexión, consulte el tema [identidad de servicio y autenticación](../feature-details/service-identity-and-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="1948b-190">For more information about endpoint identity, see the [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md) topic.</span></span>

    8. <span data-ttu-id="1948b-191">Ejecute Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1948b-191">Run Client.exe from a command prompt.</span></span>

### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1948b-192">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1948b-192">To clean up after the sample</span></span>

- <span data-ttu-id="1948b-193">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1948b-193">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>
