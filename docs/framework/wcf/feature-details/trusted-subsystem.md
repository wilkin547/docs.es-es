---
description: 'Más información acerca de: subsistema de confianza'
title: Subsistema de confianza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f5ce46b-e259-4bc9-a0b9-89d06fc9341c
ms.openlocfilehash: 41c2943c7794206dba06ef8b5bbee762931ce0c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733052"
---
# <a name="trusted-subsystem"></a><span data-ttu-id="50c10-103">Subsistema de confianza</span><span class="sxs-lookup"><span data-stu-id="50c10-103">Trusted Subsystem</span></span>

<span data-ttu-id="50c10-104">Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red.</span><span class="sxs-lookup"><span data-stu-id="50c10-104">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="50c10-105">Los servicios Web están diseñados para que el acceso a recursos adicionales (como bases de datos u otros servicios Web) se encapsule en la lógica empresarial del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="50c10-105">The Web services are designed so that access to additional resources (such as databases or other Web services) is encapsulated in the business logic of the Web service.</span></span> <span data-ttu-id="50c10-106">Estos recursos deben protegerse frente al acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="50c10-106">These resources must be protected against unauthorized access.</span></span> <span data-ttu-id="50c10-107">La siguiente ilustración describe un proceso de subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="50c10-107">The following illustration depicts a trusted subsystem process.</span></span>  
  
 <span data-ttu-id="50c10-108">![Subsistema de confianza](media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span><span class="sxs-lookup"><span data-stu-id="50c10-108">![Trusted subsystem](media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span></span>  
  
 <span data-ttu-id="50c10-109">Los siguientes pasos describen el proceso del subsistema de confianza tal y como se ilustra:</span><span class="sxs-lookup"><span data-stu-id="50c10-109">The following steps describe the trusted subsystem process as illustrated:</span></span>  
  
1. <span data-ttu-id="50c10-110">El cliente envía una solicitud al subsistema de confianza, junto con las credenciales.</span><span class="sxs-lookup"><span data-stu-id="50c10-110">The client submits a request to the trusted subsystem, along with credentials.</span></span>  
  
2. <span data-ttu-id="50c10-111">El subsistema de confianza autentica y autoriza al usuario.</span><span class="sxs-lookup"><span data-stu-id="50c10-111">The trusted subsystem authenticates and authorizes the user.</span></span>  
  
3. <span data-ttu-id="50c10-112">El subsistema de confianza envía un mensaje de solicitud al recurso remoto.</span><span class="sxs-lookup"><span data-stu-id="50c10-112">The trusted subsystem sends a request message to the remote resource.</span></span> <span data-ttu-id="50c10-113">Las credenciales acompañan a esta solicitud para el subsistema de confianza (o la cuenta de servicio bajo la que se ejecuta el proceso del subsistema de confianza).</span><span class="sxs-lookup"><span data-stu-id="50c10-113">This request is accompanied by the credentials for the trusted subsystem (or the service account under which the trusted subsystem process is being executed).</span></span>  
  
4. <span data-ttu-id="50c10-114">El recurso de back-end autentica y autoriza al subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="50c10-114">The back-end resource authenticates and authorizes the trusted subsystem.</span></span> <span data-ttu-id="50c10-115">A continuación, procesa la solicitud y emite una respuesta al subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="50c10-115">It then processes the request and issues a response to the trusted subsystem.</span></span>  
  
5. <span data-ttu-id="50c10-116">El subsistema de confianza procesa la respuesta y emite su propia respuesta al cliente.</span><span class="sxs-lookup"><span data-stu-id="50c10-116">The trusted subsystem processes the response and issues its own response to the client.</span></span>  
  
|<span data-ttu-id="50c10-117">Característica</span><span class="sxs-lookup"><span data-stu-id="50c10-117">Characteristic</span></span>|<span data-ttu-id="50c10-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="50c10-118">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="50c10-119">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="50c10-119">Security Mode</span></span>|<span data-ttu-id="50c10-120">Message</span><span class="sxs-lookup"><span data-stu-id="50c10-120">Message</span></span>|  
|<span data-ttu-id="50c10-121">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="50c10-121">Interoperability</span></span>|<span data-ttu-id="50c10-122">Solo Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="50c10-122">Windows Communication Foundation (WCF) only.</span></span>|  
|<span data-ttu-id="50c10-123">Autenticación (servicio)</span><span class="sxs-lookup"><span data-stu-id="50c10-123">Authentication (service)</span></span>|<span data-ttu-id="50c10-124">El servicio de token de seguridad autentica y autoriza clientes.</span><span class="sxs-lookup"><span data-stu-id="50c10-124">Security token service authenticates and authorizes clients.</span></span>|  
|<span data-ttu-id="50c10-125">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="50c10-125">Authentication (client)</span></span>|<span data-ttu-id="50c10-126">El subsistema de confianza autentica al cliente y el recurso autentica al servicio del subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="50c10-126">The trusted subsystem authenticates the client and the resource authenticates the trusted subsystem service.</span></span>|  
|<span data-ttu-id="50c10-127">Integridad</span><span class="sxs-lookup"><span data-stu-id="50c10-127">Integrity</span></span>|<span data-ttu-id="50c10-128">Sí</span><span class="sxs-lookup"><span data-stu-id="50c10-128">Yes</span></span>|  
|<span data-ttu-id="50c10-129">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="50c10-129">Confidentiality</span></span>|<span data-ttu-id="50c10-130">Sí</span><span class="sxs-lookup"><span data-stu-id="50c10-130">Yes</span></span>|  
|<span data-ttu-id="50c10-131">Transporte</span><span class="sxs-lookup"><span data-stu-id="50c10-131">Transport</span></span>|<span data-ttu-id="50c10-132">HTTP entre el cliente y el servicio del subsistema de confianza.</span><span class="sxs-lookup"><span data-stu-id="50c10-132">HTTP between client and the trusted subsystem service.</span></span><br /><br /> <span data-ttu-id="50c10-133">NET.TCP entre el servicio del subsistema de confianza y el recurso (servicio back-end).</span><span class="sxs-lookup"><span data-stu-id="50c10-133">NET.TCP between trusted subsystem service and the resource (back-end service).</span></span>|  
|<span data-ttu-id="50c10-134">Enlace</span><span class="sxs-lookup"><span data-stu-id="50c10-134">Binding</span></span>|<span data-ttu-id="50c10-135"><xref:System.ServiceModel.WSHttpBinding> etc <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="50c10-135"><xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span></span>|  
  
## <a name="resource-back-end-service"></a><span data-ttu-id="50c10-136">Recurso (servicio back-end)</span><span class="sxs-lookup"><span data-stu-id="50c10-136">Resource (Back-End Service)</span></span>  
  
### <a name="code"></a><span data-ttu-id="50c10-137">Código</span><span class="sxs-lookup"><span data-stu-id="50c10-137">Code</span></span>  

 <span data-ttu-id="50c10-138">El siguiente código muestra cómo crear un punto de conexión de servicio para el recurso, que utiliza seguridad de transporte a través del protocolo de transporte de TCP.</span><span class="sxs-lookup"><span data-stu-id="50c10-138">The following code shows how to create a service endpoint for the resource, which uses transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystemsResource#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsresource/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsResource#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsresource/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="50c10-139">Configuración</span><span class="sxs-lookup"><span data-stu-id="50c10-139">Configuration</span></span>  

 <span data-ttu-id="50c10-140">La siguiente configuración define el mismo punto de conexión mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="50c10-140">The following configuration sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.BackendService"  
               behaviorConfiguration="BackendServiceBehavior">  
        <endpoint address="net.tcp://localhost.com:8001/BackendService"  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="BackendServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, BackendService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="trusted-subsystem"></a><span data-ttu-id="50c10-141">Subsistema de confianza</span><span class="sxs-lookup"><span data-stu-id="50c10-141">Trusted Subsystem</span></span>  
  
### <a name="code"></a><span data-ttu-id="50c10-142">Código</span><span class="sxs-lookup"><span data-stu-id="50c10-142">Code</span></span>  

 <span data-ttu-id="50c10-143">El siguiente código muestra cómo crear un extremo de servicio para el subsistema de confianza que utiliza el modo de seguridad sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="50c10-143">The following code shows how to create a service endpoint for the trusted subsystem that uses message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystems#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#1)]
 [!code-vb[TrustedSubSystems#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#1)]  
  
 <span data-ttu-id="50c10-144">El siguiente código muestra un servicio en un subsistema de confianza que se comunica con un servicio back-end utilizando seguridad de transporte a través del protocolo de transporte de TCP.</span><span class="sxs-lookup"><span data-stu-id="50c10-144">The following code shows a service in a trusted subsystem that communicates with a back-end service using transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystems#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#2)]
 [!code-vb[TrustedSubSystems#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="50c10-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="50c10-145">Configuration</span></span>  

 <span data-ttu-id="50c10-146">La siguiente configuración define el mismo punto de conexión mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="50c10-146">The following configuration sets up the same endpoint using configuration.</span></span> <span data-ttu-id="50c10-147">Tenga en cuenta los dos enlaces: uno protege el servicio que se hospeda en el subsistema de confianza y el otro comunica entre el subsistema de confianza y el servicio back-end.</span><span class="sxs-lookup"><span data-stu-id="50c10-147">Note the two bindings: One secures the service hosted in the trusted subsystem and the other communicates between the trusted subsystem and the back-end service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.FacadeService"  
               behaviorConfiguration="FacadeServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/FacadeService"/>  
          </baseAddresses>  
        </host>  
        <endpoint address="http://localhost:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <client>  
      <endpoint name=""
                address="net.tcp://contoso.com:8001/BackendService"  
                binding="customBinding"  
                bindingConfiguration="ClientBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
      <customBinding>  
        <binding name="ClientBinding">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="FacadeServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                storeLocation="LocalMachine"  
                                storeName="My"  
                                x509FindType="FindBySubjectName" />  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, FacadeService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="50c10-148">Cliente</span><span class="sxs-lookup"><span data-stu-id="50c10-148">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="50c10-149">Código</span><span class="sxs-lookup"><span data-stu-id="50c10-149">Code</span></span>  

 <span data-ttu-id="50c10-150">El siguiente código muestra cómo crear el cliente que comunica con el subsistema de confianza utilizando la seguridad de mensaje sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="50c10-150">The following code shows how to create the client that communicates with the trusted subsystem by using message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystemsClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsclient/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsclient/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="50c10-151">Configuración</span><span class="sxs-lookup"><span data-stu-id="50c10-151">Configuration</span></span>  

 <span data-ttu-id="50c10-152">El siguiente código configura el cliente para utilizar la seguridad de mensaje sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="50c10-152">The following code configures the client to use message security over the HTTP protocol and a user name and password for authentication.</span></span> <span data-ttu-id="50c10-153">El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).</span><span class="sxs-lookup"><span data-stu-id="50c10-153">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <client>  
        <endpoint name=""
                  address="http://www.cohowinery.com:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientUserNameBehavior"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientUserNameBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50c10-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c10-154">See also</span></span>

- [<span data-ttu-id="50c10-155">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="50c10-155">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="50c10-156">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="50c10-156">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
