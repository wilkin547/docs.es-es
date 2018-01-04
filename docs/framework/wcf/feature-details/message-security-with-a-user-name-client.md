---
title: Seguridad de los mensajes con un cliente de nombres de usuario
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: dfda34c6bf165ebcecfd6d9a3710e785586d6cb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="a7ed1-102">Seguridad de los mensajes con un cliente de nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="a7ed1-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="a7ed1-103">La ilustración siguiente muestra un servicio y cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protegidos mediante seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-103">The following illustration shows an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message-level security.</span></span> <span data-ttu-id="a7ed1-104">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="a7ed1-105">El cliente se autentica utilizando un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="a7ed1-106">Para una aplicación de ejemplo, vea [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="a7ed1-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="a7ed1-107">![Seguridad de mensaje mediante la autenticación de nombre de usuario](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="a7ed1-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="a7ed1-108">Característica</span><span class="sxs-lookup"><span data-stu-id="a7ed1-108">Characteristic</span></span>|<span data-ttu-id="a7ed1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7ed1-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a7ed1-110">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="a7ed1-110">Security Mode</span></span>|<span data-ttu-id="a7ed1-111">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a7ed1-111">Message</span></span>|  
|<span data-ttu-id="a7ed1-112">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="a7ed1-112">Interoperability</span></span>|<span data-ttu-id="a7ed1-113">Solo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ed1-113">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] only</span></span>|  
|<span data-ttu-id="a7ed1-114">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="a7ed1-114">Authentication (Server)</span></span>|<span data-ttu-id="a7ed1-115">La negociación inicial requiere autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="a7ed1-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="a7ed1-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="a7ed1-116">Authentication (Client)</span></span>|<span data-ttu-id="a7ed1-117">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="a7ed1-117">User name/password</span></span>|  
|<span data-ttu-id="a7ed1-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="a7ed1-118">Integrity</span></span>|<span data-ttu-id="a7ed1-119">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="a7ed1-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="a7ed1-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a7ed1-120">Confidentiality</span></span>|<span data-ttu-id="a7ed1-121">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="a7ed1-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="a7ed1-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="a7ed1-122">Transport</span></span>|<span data-ttu-id="a7ed1-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="a7ed1-123">HTTP</span></span>|  
|<span data-ttu-id="a7ed1-124">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a7ed1-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="a7ed1-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="a7ed1-125">Service</span></span>  
 <span data-ttu-id="a7ed1-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="a7ed1-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a7ed1-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="a7ed1-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="a7ed1-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a7ed1-130">Código</span><span class="sxs-lookup"><span data-stu-id="a7ed1-130">Code</span></span>  
 <span data-ttu-id="a7ed1-131">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="a7ed1-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="a7ed1-132">Configuration</span></span>  
 <span data-ttu-id="a7ed1-133">La siguiente configuración se puede usar en lugar del código.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-133">The following configuration can be used instead of the code:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="a7ed1-134">Cliente</span><span class="sxs-lookup"><span data-stu-id="a7ed1-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="a7ed1-135">Código</span><span class="sxs-lookup"><span data-stu-id="a7ed1-135">Code</span></span>  
 <span data-ttu-id="a7ed1-136">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-136">The following code creates the client.</span></span> <span data-ttu-id="a7ed1-137">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="a7ed1-138">El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).</span><span class="sxs-lookup"><span data-stu-id="a7ed1-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="a7ed1-139">El código para devolver el nombre de usuario y la contraseña no se muestra aquí porque se debe hacer en el nivel de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="a7ed1-140">Por ejemplo, use un cuadro de diálogo de Windows Forms para solicitar los datos al usuario.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="a7ed1-141">Configuración</span><span class="sxs-lookup"><span data-stu-id="a7ed1-141">Configuration</span></span>  
 <span data-ttu-id="a7ed1-142">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-142">The following code configures the client.</span></span> <span data-ttu-id="a7ed1-143">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a7ed1-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="a7ed1-144">El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).</span><span class="sxs-lookup"><span data-stu-id="a7ed1-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a7ed1-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7ed1-145">See Also</span></span>  
 [<span data-ttu-id="a7ed1-146">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a7ed1-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="a7ed1-147">Nombre de usuario de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7ed1-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="a7ed1-148">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="a7ed1-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a7ed1-149">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="a7ed1-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="a7ed1-150">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="a7ed1-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
