---
title: Seguridad de los mensajes con un cliente de nombres de usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7bda1bc18e2b5af1365c799c6f2be9d8d220e9ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495137"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="820f0-102">Seguridad de los mensajes con un cliente de nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="820f0-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="820f0-103">La ilustración siguiente muestra un servicio de Windows Communication Foundation (WCF) y el cliente que se protegen utilizando la seguridad de nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="820f0-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="820f0-104">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="820f0-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="820f0-105">El cliente se autentica utilizando un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="820f0-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="820f0-106">Para una aplicación de ejemplo, vea [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="820f0-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="820f0-107">![Seguridad de mensaje mediante la autenticación de nombre de usuario](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="820f0-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="820f0-108">Característica</span><span class="sxs-lookup"><span data-stu-id="820f0-108">Characteristic</span></span>|<span data-ttu-id="820f0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="820f0-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="820f0-110">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="820f0-110">Security Mode</span></span>|<span data-ttu-id="820f0-111">Mensaje</span><span class="sxs-lookup"><span data-stu-id="820f0-111">Message</span></span>|  
|<span data-ttu-id="820f0-112">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="820f0-112">Interoperability</span></span>|<span data-ttu-id="820f0-113">Windows Communication Foundation (WCF) solo</span><span class="sxs-lookup"><span data-stu-id="820f0-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="820f0-114">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="820f0-114">Authentication (Server)</span></span>|<span data-ttu-id="820f0-115">La negociación inicial requiere autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="820f0-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="820f0-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="820f0-116">Authentication (Client)</span></span>|<span data-ttu-id="820f0-117">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="820f0-117">User name/password</span></span>|  
|<span data-ttu-id="820f0-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="820f0-118">Integrity</span></span>|<span data-ttu-id="820f0-119">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="820f0-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="820f0-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="820f0-120">Confidentiality</span></span>|<span data-ttu-id="820f0-121">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="820f0-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="820f0-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="820f0-122">Transport</span></span>|<span data-ttu-id="820f0-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="820f0-123">HTTP</span></span>|  
|<span data-ttu-id="820f0-124">Enlaces</span><span class="sxs-lookup"><span data-stu-id="820f0-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="820f0-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="820f0-125">Service</span></span>  
 <span data-ttu-id="820f0-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="820f0-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="820f0-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="820f0-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="820f0-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="820f0-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="820f0-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="820f0-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="820f0-130">Código</span><span class="sxs-lookup"><span data-stu-id="820f0-130">Code</span></span>  
 <span data-ttu-id="820f0-131">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="820f0-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="820f0-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="820f0-132">Configuration</span></span>  
 <span data-ttu-id="820f0-133">La siguiente configuración se puede usar en lugar del código.</span><span class="sxs-lookup"><span data-stu-id="820f0-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="820f0-134">Cliente</span><span class="sxs-lookup"><span data-stu-id="820f0-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="820f0-135">Código</span><span class="sxs-lookup"><span data-stu-id="820f0-135">Code</span></span>  
 <span data-ttu-id="820f0-136">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="820f0-136">The following code creates the client.</span></span> <span data-ttu-id="820f0-137">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.</span><span class="sxs-lookup"><span data-stu-id="820f0-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="820f0-138">El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).</span><span class="sxs-lookup"><span data-stu-id="820f0-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="820f0-139">El código para devolver el nombre de usuario y la contraseña no se muestra aquí porque se debe hacer en el nivel de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="820f0-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="820f0-140">Por ejemplo, use un cuadro de diálogo de Windows Forms para solicitar los datos al usuario.</span><span class="sxs-lookup"><span data-stu-id="820f0-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="820f0-141">Configuración</span><span class="sxs-lookup"><span data-stu-id="820f0-141">Configuration</span></span>  
 <span data-ttu-id="820f0-142">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="820f0-142">The following code configures the client.</span></span> <span data-ttu-id="820f0-143">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.</span><span class="sxs-lookup"><span data-stu-id="820f0-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="820f0-144">El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).</span><span class="sxs-lookup"><span data-stu-id="820f0-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="820f0-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="820f0-145">See Also</span></span>  
 [<span data-ttu-id="820f0-146">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="820f0-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="820f0-147">Nombre de usuario de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="820f0-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="820f0-148">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="820f0-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="820f0-149">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="820f0-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="820f0-150">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="820f0-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
