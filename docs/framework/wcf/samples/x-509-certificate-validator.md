---
title: Validador de certificado X.509
ms.date: 03/30/2017
ms.assetid: 3b042379-02c4-4395-b927-e57c842fd3e0
ms.openlocfilehash: 32d99b93ef014967aa04bc70f73fbd2ebcfe2c60
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594834"
---
# <a name="x509-certificate-validator"></a><span data-ttu-id="9f035-102">Validador de certificado X.509</span><span class="sxs-lookup"><span data-stu-id="9f035-102">X.509 Certificate Validator</span></span>

<span data-ttu-id="9f035-103">Este ejemplo muestra cómo implementar un validador de certificado X.509 personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f035-103">This sample demonstrates how to implement a custom X.509 Certificate Validator.</span></span> <span data-ttu-id="9f035-104">Esto es útil en casos donde ninguno de los modos de validación de certificado X.509 integrado es adecuado para los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9f035-104">This is useful in cases where none of the built-in X.509 Certificate Validation modes is appropriate for the requirements of the application.</span></span> <span data-ttu-id="9f035-105">Este ejemplo muestra un servicio que tiene un validador personalizado que acepta certificados emitidos por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="9f035-105">This sample shows a service that has a custom validator that accepts self-issued certificates.</span></span> <span data-ttu-id="9f035-106">El cliente utiliza un certificado para autenticar al servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-106">The client uses such a certificate to authenticate to the service.</span></span>

<span data-ttu-id="9f035-107">Nota: como cualquiera puede construir un certificado emitido por sí mismo, el validador personalizado utilizado por el servicio es menos seguro que el comportamiento predeterminado proporcionado por X509CertificateValidationMode de ChainTrust.</span><span class="sxs-lookup"><span data-stu-id="9f035-107">Note: As anyone can construct a self-issued certificate the custom validator used by the service is less secure than the default behavior provided by the ChainTrust X509CertificateValidationMode.</span></span> <span data-ttu-id="9f035-108">Las implicaciones de seguridad que conlleva deberían considerarse cuidadosamente antes de utilizar esta lógica de validación en el código de producción.</span><span class="sxs-lookup"><span data-stu-id="9f035-108">The security implications of this should be carefully considered before using this validation logic in production code.</span></span>

<span data-ttu-id="9f035-109">En resumen, este ejemplo muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="9f035-109">In summary this sample demonstrates how:</span></span>

- <span data-ttu-id="9f035-110">El cliente se puede autenticar utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="9f035-110">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="9f035-111">El servidor valida las credenciales del cliente contra un X509CertificateValidator personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f035-111">The server validates the client credentials against a custom X509CertificateValidator.</span></span>

- <span data-ttu-id="9f035-112">El servidor se autentica utilizando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-112">The server is authenticated using the server's X.509 certificate.</span></span>

<span data-ttu-id="9f035-113">El servicio expone un punto de conexión único para comunicarse con el servicio, definido mediante el archivo de configuración app. config. El punto de conexión consta de una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="9f035-113">The service exposes a single endpoint for communicating with the service, defined using the configuration file App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="9f035-114">El enlace se configura con un estándar `wsHttpBinding` que tiene como valor predeterminado el uso de `WSSecurity` y la autenticación de certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-114">The binding is configured with a standard `wsHttpBinding` that defaults to using `WSSecurity` and client certificate authentication.</span></span> <span data-ttu-id="9f035-115">El comportamiento del servicio especifica el modo Personalizado para validar los certificados X.509 junto con el tipo de la clase de validador.</span><span class="sxs-lookup"><span data-stu-id="9f035-115">The service behavior specifies the Custom mode for validating client X.509 certificates along with the type of the validator class.</span></span> <span data-ttu-id="9f035-116">El comportamiento también especifica el certificado del servidor mediante el elemento serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="9f035-116">The behavior also specifies the server certificate using the serviceCertificate element.</span></span> <span data-ttu-id="9f035-117">El certificado de servidor debe contener el mismo valor para el `SubjectName` que `findValue` en el [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="9f035-117">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- use host/baseAddresses to configure base address -->
        <!-- provided by host -->
        <host>
          <baseAddresses>
            <add baseAddress =
                "http://localhost:8001/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address specified above, provide one endpoint -->
        <endpoint address="certificate"
               binding="wsHttpBinding"
               bindingConfiguration="Binding"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <!-- X509 certificate binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults ="true"/>
          <serviceCredentials>
            <!-- The serviceCredentials behavior allows one -->
            <!-- to specify authentication constraints on -->
            <!-- client certificates. -->
            <clientCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- Custom means that if the custom -->
              <!-- X509CertificateValidator does NOT throw -->
              <!-- an exception, then the provided certificate -->
              <!-- will be trusted without performing any -->
              <!-- validation beyond that performed by the custom -->
              <!-- validator. The security implications of this -->
              <!-- setting should be carefully considered before -->
              <!-- using Custom in production code. -->
              <authentication
                 certificateValidationMode="Custom"
                 customCertificateValidatorType =
"Microsoft.ServiceModel.Samples.CustomX509CertificateValidator, service" />
            </clientCertificate>
            <!-- The serviceCredentials behavior allows one to -->
            <!-- define a service certificate. -->
            <!-- A service certificate is used by a client to -->
            <!-- authenticate the service and provide message -->
            <!-- protection. This configuration references the -->
            <!-- "localhost" certificate installed during the setup -->
            <!-- instructions. -->
            <serviceCertificate findValue="localhost"
                 storeLocation="LocalMachine"
                 storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
      </system.serviceModel>
```

<span data-ttu-id="9f035-118">La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="9f035-118">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="9f035-119">El enlace del cliente se configura con el modo adecuado y el `clientCredentialType` del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9f035-119">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>

```xml
<system.serviceModel>
    <client>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
        address=
        "http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>
    <bindings>
        <wsHttpBinding>
            <!-- X509 certificate binding -->
            <binding name="Binding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
               </security>
            </binding>
       </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- PeerOrChainTrust means that if the certificate -->
              <!-- is in the user's Trusted People store, then it -->
              <!-- is trusted without performing a validation of -->
              <!-- the certificate's issuer chain. -->
              <!-- This setting is used here for convenience so -->
              <!-- that the sample can be run without having to -->
              <!-- have certificates issued by a certification -->
              <!-- authority (CA). This setting is less secure -->
              <!-- than the default, ChainTrust. The security -->
              <!-- implications of this setting should be -->
              <!-- carefully considered before using -->
              <!-- PeerOrChainTrust in production code.-->
              <authentication
                  certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>
```

<span data-ttu-id="9f035-120">La implementación del cliente establece el certificado de cliente que utilizar.</span><span class="sxs-lookup"><span data-stu-id="9f035-120">The client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client = new CalculatorClient("Certificate");
try
{
    client.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
    client.Close();
}
catch (TimeoutException e)
{
    Console.WriteLine("Call timed out : {0}", e.Message);
    client.Abort();
}
catch (CommunicationException e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
```

<span data-ttu-id="9f035-121">Este ejemplo utiliza un X509CertificateValidator personalizado para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="9f035-121">This sample uses a custom X509CertificateValidator to validate certificates.</span></span> <span data-ttu-id="9f035-122">El ejemplo implementa CustomX509CertificateValidator, derivado de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="9f035-122">The sample implements CustomX509CertificateValidator, derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="9f035-123">Consulte la documentación sobre <xref:System.IdentityModel.Selectors.X509CertificateValidator> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9f035-123">See documentation about <xref:System.IdentityModel.Selectors.X509CertificateValidator> for more information.</span></span> <span data-ttu-id="9f035-124">Este ejemplo de validador personalizado determinado implementa el método Validate para aceptar cualquier certificado X.509 que se emita por sí mismo tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f035-124">This particular custom validator sample implements the Validate method to accept any X.509 certificate that is self-issued as shown in the following code.</span></span>

```csharp
public class CustomX509CertificateValidator : X509CertificateValidator
{
  public override void Validate ( X509Certificate2 certificate )
  {
   // Only accept self-issued certificates
   if (certificate.Subject != certificate.Issuer)
     throw new Exception("Certificate is not self-issued");
   }
}
```

 <span data-ttu-id="9f035-125">Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9f035-125">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="9f035-126">Esto se hace mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f035-126">This is done using the following code.</span></span>

```csharp
serviceHost.Credentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.Custom;
serviceHost.Credentials.ClientCertificate.Authentication.CustomCertificateValidator = new CustomX509CertificateValidator();
```

 <span data-ttu-id="9f035-127">O puede hacer lo mismo en la configuración tal y como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9f035-127">Or you can do the same thing in configuration as follows.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
     <behavior name="CalculatorServiceBehavior">
       ...
   <serviceCredentials>
    <!--The serviceCredentials behavior allows one to specify -->
    <!--authentication constraints on client certificates.-->
    <clientCertificate>
    <!-- Setting the certificateValidationMode to Custom means -->
    <!--that if the custom X509CertificateValidator does NOT -->
    <!--throw an exception, then the provided certificate will -->
    <!--be trusted without performing any validation beyond that -->
    <!--performed by the custom validator. The security -->
    <!--implications of this setting should be carefully -->
    <!--considered before using Custom in production code. -->
    <authentication certificateValidationMode="Custom"
       customCertificateValidatorType =
"Microsoft.ServiceModel.Samples. CustomX509CertificateValidator, service" />
   </clientCertificate>
   </serviceCredentials>
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="9f035-128">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9f035-129">El cliente debería llamar correctamente a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="9f035-129">The client should successfully call all the methods.</span></span> <span data-ttu-id="9f035-130">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-130">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="9f035-131">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="9f035-131">Setup Batch File</span></span>

<span data-ttu-id="9f035-132">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-132">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="9f035-133">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="9f035-133">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="9f035-134">A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:</span><span class="sxs-lookup"><span data-stu-id="9f035-134">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="9f035-135">Crear el certificado de servidor:</span><span class="sxs-lookup"><span data-stu-id="9f035-135">Creating the server certificate:</span></span>

     <span data-ttu-id="9f035-136">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9f035-136">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="9f035-137">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-137">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="9f035-138">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-138">Change this variable to specify your own server name.</span></span> <span data-ttu-id="9f035-139">El valor predeterminado es el host local.</span><span class="sxs-lookup"><span data-stu-id="9f035-139">The default value is localhost.</span></span>

    ```bash
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="9f035-140">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:</span><span class="sxs-lookup"><span data-stu-id="9f035-140">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="9f035-141">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-141">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="9f035-142">Se requiere este paso ya que los certificados generados por Makecert.exe no son de la confianza del sistema cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-142">This step is required since certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="9f035-143">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-143">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```bash
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="9f035-144">Crear el certificado del cliente:</span><span class="sxs-lookup"><span data-stu-id="9f035-144">Creating the client certificate:</span></span>

     <span data-ttu-id="9f035-145">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9f035-145">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="9f035-146">La variable %USER_NAME% especifica el nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-146">The %USER_NAME% variable specifies the client name.</span></span> <span data-ttu-id="9f035-147">Este valor está establecido en "test1" porque se trata del nombre que busca el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-147">This value is set to "test1" because this is the name the client code looks for.</span></span> <span data-ttu-id="9f035-148">Si cambia el valor de %USER_NAME% debe cambiar el valor correspondiente en el archivo de origen Client.cs y recompilar el cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-148">If you change the value of %USER_NAME% you must change the corresponding value in the Client.cs source file and rebuild the client.</span></span>

     <span data-ttu-id="9f035-149">El certificado está almacenado en Mi almacén (Personal) debajo de la ubicación de almacén CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="9f035-149">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```bash
    echo ************
    echo Client cert setup starting
    echo %USER_NAME%
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="9f035-150">Instalar el certificado del cliente en el almacén de certificados de confianza del servidor:</span><span class="sxs-lookup"><span data-stu-id="9f035-150">Installing the client certificate into server's trusted certificate store:</span></span>

     <span data-ttu-id="9f035-151">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado del cliente en el almacén de los usuarios de confianza.</span><span class="sxs-lookup"><span data-stu-id="9f035-151">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="9f035-152">Se requiere este paso porque el sistema servidor no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="9f035-152">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="9f035-153">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-153">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```bash
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="9f035-154">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f035-154">To set up and build the sample</span></span>

1. <span data-ttu-id="9f035-155">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9f035-155">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="9f035-156">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9f035-156">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="9f035-157">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="9f035-157">To run the sample on the same computer</span></span>

1. <span data-ttu-id="9f035-158">Ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9f035-158">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="9f035-159">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9f035-159">This installs all the certificates required for running the sample.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9f035-160">El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="9f035-160">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="9f035-161">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="9f035-161">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="9f035-162">Inicie Service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="9f035-162">Launch Service.exe from service\bin.</span></span>

3. <span data-ttu-id="9f035-163">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="9f035-163">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="9f035-164">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-164">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="9f035-165">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9f035-165">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="9f035-166">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="9f035-166">To run the sample across computers</span></span>

1. <span data-ttu-id="9f035-167">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-167">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="9f035-168">Copie los archivos de programa de servicio desde \service\bin en el directorio virtual del equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-168">Copy the service program files from \service\bin to the virtual directory on the service computer.</span></span> <span data-ttu-id="9f035-169">Copie también los archivos Setup.bat, Cleanup.bat, GetComputerName.vbs e ImportClientCert.bat en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-169">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="9f035-170">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-170">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="9f035-171">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-171">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="9f035-172">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-172">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="9f035-173">En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9f035-173">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="9f035-174">`setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="9f035-174">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>

6. <span data-ttu-id="9f035-175">Edite Service. exe. config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="9f035-175">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="9f035-176">Cambie también el nombre del equipo en el \<service> / \<baseAddresses> elemento de localhost al nombre completo de su equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-176">Also change the computer name in the \<service>/\<baseAddresses> element from localhost to fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="9f035-177">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="9f035-177">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="9f035-178">En el cliente, ejecute `setup.bat client` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9f035-178">On the client, run `setup.bat client` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="9f035-179">Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.</span><span class="sxs-lookup"><span data-stu-id="9f035-179">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>

9. <span data-ttu-id="9f035-180">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="9f035-180">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="9f035-181">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-181">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>

10. <span data-ttu-id="9f035-182">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9f035-182">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="9f035-183">En el cliente, ejecute ImportServiceCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9f035-183">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="9f035-184">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9f035-184">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>

12. <span data-ttu-id="9f035-185">En el servidor, ejecute ImportClientCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9f035-185">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="9f035-186">De esta forma se importa el certificado del cliente desde el archivo Client.cer al almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9f035-186">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>

13. <span data-ttu-id="9f035-187">En el equipo servidor, inicie Service.exe desde la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f035-187">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="9f035-188">En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f035-188">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="9f035-189">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9f035-189">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="9f035-190">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f035-190">To clean up after the sample</span></span>

1. <span data-ttu-id="9f035-191">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9f035-191">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="9f035-192">Esto quita los certificados de cliente y servidor del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="9f035-192">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="9f035-193">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="9f035-193">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="9f035-194">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9f035-194">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="9f035-195">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="9f035-195">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
