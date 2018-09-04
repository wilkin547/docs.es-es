---
title: Enlace HTTP de federación de WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 53f2cb893476cdfa0517bd6586f38951dff1f2af
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513067"
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="8fee7-102">Enlace HTTP de federación de WS 2007</span><span class="sxs-lookup"><span data-stu-id="8fee7-102">WS 2007 Federation HTTP Binding</span></span>
<span data-ttu-id="8fee7-103">Este ejemplo muestra el uso de <xref:System.ServiceModel.WS2007FederationHttpBinding>, un enlace estándar que puede utilizar para generar escenarios federados que admiten la versión 1.3 de la especificación WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="8fee7-103">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fee7-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8fee7-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8fee7-105">El ejemplo está compuesto de un programa cliente basado (Client.exe) en consola, un programa de servicio de token de seguridad basado (Securitytokenservice.exe) en consola y un programa de servicio basado (Service.exe) en consola.</span><span class="sxs-lookup"><span data-stu-id="8fee7-105">The sample consists of a console-based client program (Client.exe), a console-based security token service program (Securitytokenservice.exe), and a console-based service program (Service.exe).</span></span> <span data-ttu-id="8fee7-106">El servicio implementa un contrato que define un patrón de comunicación de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="8fee7-106">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="8fee7-107">La interfaz `ICalculator`, que expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`) define el contrato.</span><span class="sxs-lookup"><span data-stu-id="8fee7-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="8fee7-108">El cliente obtiene un token de seguridad del Servicio de token de seguridad (STS) y realiza las solicitudes sincrónicas al servicio para una operación matemática determinada.</span><span class="sxs-lookup"><span data-stu-id="8fee7-108">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="8fee7-109">El servicio responde a continuación con el resultado.</span><span class="sxs-lookup"><span data-stu-id="8fee7-109">The service then replies with the result.</span></span> <span data-ttu-id="8fee7-110">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="8fee7-110">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="8fee7-111">El ejemplo pone el contrato `ICalculator` disponible mediante el elemento `ws2007FederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8fee7-111">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="8fee7-112">La configuración de este enlace en el cliente se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8fee7-112">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="8fee7-113">En el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), el `security` valor especifica que se debe usar el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8fee7-113">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="8fee7-114">En este ejemplo, `message` utiliza la seguridad, que es el motivo por el [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) se especifican dentro la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8fee7-114">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="8fee7-115">El [ \<emisor >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) elemento dentro de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección y el enlace para STS que emite un token de seguridad para el cliente para que el cliente pueda autenticarse en el `ICalculator` service.</span><span class="sxs-lookup"><span data-stu-id="8fee7-115">The [\<issuer>](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>  
  
 <span data-ttu-id="8fee7-116">La configuración de este enlace en el servicio se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8fee7-116">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="8fee7-117">En el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), el `security` valor especifica que se debe usar el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8fee7-117">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="8fee7-118">En este ejemplo, `message` utiliza la seguridad, que es el motivo por el [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) se especifican dentro la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8fee7-118">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="8fee7-119">El [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) elemento de `ws2007FederationHttpBinding` dentro de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección e identidad para un punto de conexión que puede usarse para recuperar metadatos para STS.</span><span class="sxs-lookup"><span data-stu-id="8fee7-119">The [\<issuerMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>  
  
 <span data-ttu-id="8fee7-120">El comportamiento para el servicio se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8fee7-120">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="8fee7-121">El [ \<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> permite al servicio especificar las restricciones en los tokens y permite a los clientes presentarse durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8fee7-121">The [\<issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="8fee7-122">Esta configuración especifica que el servicio acepta los tokens firmados por un certificado cuyo nombre de asunto sea CN=STS.</span><span class="sxs-lookup"><span data-stu-id="8fee7-122">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="8fee7-123">STS hace que esté disponible un extremo único mediante el estándar <xref:System.ServiceModel.WS2007HttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="8fee7-123">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="8fee7-124">El servicio responde a las solicitudes de los clientes para los tokens.</span><span class="sxs-lookup"><span data-stu-id="8fee7-124">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="8fee7-125">Si el cliente se autentica utilizando una cuenta de Windows, el servicio emite un token que contiene el nombre de usuario del cliente como una demanda.</span><span class="sxs-lookup"><span data-stu-id="8fee7-125">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="8fee7-126">Como parte de la creación del token, el STS firma el token usando la clave privada asociada con el certificado de CN=STS.</span><span class="sxs-lookup"><span data-stu-id="8fee7-126">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="8fee7-127">Además, crea una clave simétrica y la cifra utilizando la clave pública asociada con el certificado de CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="8fee7-127">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="8fee7-128">Para devolver el token al cliente, el STS devuelve también la clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="8fee7-128">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="8fee7-129">El cliente presenta el token emitido al servicio `ICalculator` y demuestra que conoce la clave simétrica firmando el mensaje con esa clave.</span><span class="sxs-lookup"><span data-stu-id="8fee7-129">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
 <span data-ttu-id="8fee7-130">Al ejecutar el ejemplo, la solicitud para el token de seguridad se muestra en la ventana de la consola del STS.</span><span class="sxs-lookup"><span data-stu-id="8fee7-130">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="8fee7-131">Las solicitudes y respuestas de la operación se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="8fee7-131">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="8fee7-132">Presione ENTRAR en cualquiera de las ventanas de la consola para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8fee7-132">Press ENTER in any of the console windows to shut down the application.</span></span>  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 <span data-ttu-id="8fee7-133">El archivo Setup.bat incluido con este ejemplo le permite configurar el servidor y el STS con los certificados pertinentes para ejecutan una aplicación autohospedada.</span><span class="sxs-lookup"><span data-stu-id="8fee7-133">The Setup.bat file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="8fee7-134">El archivo por lotes crea dos certificados en el almacén de certificados LocalMachine /TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="8fee7-134">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="8fee7-135">El primer certificado tiene un nombre sujeto de CN=STS y STS lo utiliza para firmar los tokens de seguridad que emite al cliente.</span><span class="sxs-lookup"><span data-stu-id="8fee7-135">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="8fee7-136">El segundo certificado tiene un nombre sujeto de CN=localhost y el STS lo utiliza para cifrar en cierto modo una clave que el servicio puede descifrar.</span><span class="sxs-lookup"><span data-stu-id="8fee7-136">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8fee7-137">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8fee7-137">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8fee7-138">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8fee7-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8fee7-139">Abra un símbolo del sistema de Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat para crear los certificados necesarios.</span><span class="sxs-lookup"><span data-stu-id="8fee7-139">Open a Visual Studio command prompt with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>  
  
 <span data-ttu-id="8fee7-140">Este archivo por lotes utiliza Certmgr.exe y Makecert.exe, que se distribuyen con Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="8fee7-140">This batch file uses Certmgr.exe and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="8fee7-141">Sin embargo, debe ejecutar Setup.bat desde un símbolo del sistema de Visual Studio para que el script pueda encontrar estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="8fee7-141">However, you must run Setup.bat from within a Visual Studio  command prompt to enable the script to find these tools.</span></span>  
  
1.  <span data-ttu-id="8fee7-142">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8fee7-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="8fee7-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8fee7-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="8fee7-144">Si usas [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], debe ejecutar Service.exe, Client.exe y SecurityTokenService.exe con privilegios elevados (haga clic en los archivos y, a continuación, haga clic en **ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="8fee7-144">If you are using [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must run Service.exe, Client.exe, and SecurityTokenService.exe with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8fee7-145">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8fee7-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8fee7-146">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8fee7-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8fee7-147">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8fee7-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8fee7-148">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8fee7-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
## <a name="see-also"></a><span data-ttu-id="8fee7-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fee7-149">See Also</span></span>
