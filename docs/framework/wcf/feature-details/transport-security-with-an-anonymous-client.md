---
title: "Seguridad del transporte con clientes anónimos"
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
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a4d4180a0a60e062ab6d8872b153d5bc8b416708
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="27d21-102">Seguridad del transporte con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="27d21-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="27d21-103">Este escenario de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza la seguridad del transporte (HTTPS) para garantizar la confidencialidad y la integridad.</span><span class="sxs-lookup"><span data-stu-id="27d21-103">This [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="27d21-104">El servidor debe autenticarse con un certificado de Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="27d21-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="27d21-105">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="27d21-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="27d21-106">Para una aplicación de ejemplo, vea [seguridad de transporte WS](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="27d21-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="27d21-107">seguridad de transporte, consulte [información general sobre la seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27d21-107"> transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="27d21-108">uso de un certificado con un servicio, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="27d21-108"> using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="27d21-109">![Usar seguridad de transporte con un cliente anónimo](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="27d21-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="27d21-110">Característica</span><span class="sxs-lookup"><span data-stu-id="27d21-110">Characteristic</span></span>|<span data-ttu-id="27d21-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="27d21-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="27d21-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="27d21-112">Security Mode</span></span>|<span data-ttu-id="27d21-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="27d21-113">Transport</span></span>|  
|<span data-ttu-id="27d21-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="27d21-114">Interoperability</span></span>|<span data-ttu-id="27d21-115">Con servicios y clientes Web existentes</span><span class="sxs-lookup"><span data-stu-id="27d21-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="27d21-116">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="27d21-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="27d21-117">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="27d21-117">Authentication (Client)</span></span>|<span data-ttu-id="27d21-118">Sí</span><span class="sxs-lookup"><span data-stu-id="27d21-118">Yes</span></span><br /><br /> <span data-ttu-id="27d21-119">Nivel de aplicación (no se admite [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)])</span><span class="sxs-lookup"><span data-stu-id="27d21-119">Application level (no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] support)</span></span>|  
|<span data-ttu-id="27d21-120">Integridad</span><span class="sxs-lookup"><span data-stu-id="27d21-120">Integrity</span></span>|<span data-ttu-id="27d21-121">Sí</span><span class="sxs-lookup"><span data-stu-id="27d21-121">Yes</span></span>|  
|<span data-ttu-id="27d21-122">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="27d21-122">Confidentiality</span></span>|<span data-ttu-id="27d21-123">Sí</span><span class="sxs-lookup"><span data-stu-id="27d21-123">Yes</span></span>|  
|<span data-ttu-id="27d21-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="27d21-124">Transport</span></span>|<span data-ttu-id="27d21-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="27d21-125">HTTPS</span></span>|  
|<span data-ttu-id="27d21-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="27d21-126">Binding</span></span>|<span data-ttu-id="27d21-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="27d21-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="27d21-128">Servicio</span><span class="sxs-lookup"><span data-stu-id="27d21-128">Service</span></span>  
 <span data-ttu-id="27d21-129">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="27d21-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="27d21-130">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="27d21-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="27d21-131">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="27d21-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="27d21-132">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="27d21-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="27d21-133">Código</span><span class="sxs-lookup"><span data-stu-id="27d21-133">Code</span></span>  
 <span data-ttu-id="27d21-134">El código siguiente muestra cómo crear un punto de conexión mediante la seguridad del transporte:</span><span class="sxs-lookup"><span data-stu-id="27d21-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="27d21-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="27d21-135">Configuration</span></span>  
 <span data-ttu-id="27d21-136">El código siguiente configura el mismo extremo mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="27d21-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="27d21-137">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="27d21-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="27d21-138">Cliente</span><span class="sxs-lookup"><span data-stu-id="27d21-138">Client</span></span>  
 <span data-ttu-id="27d21-139">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="27d21-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="27d21-140">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="27d21-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="27d21-141">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="27d21-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="27d21-142">Cree un cliente que no defina direcciones de extremo.</span><span class="sxs-lookup"><span data-stu-id="27d21-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="27d21-143">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="27d21-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="27d21-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27d21-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="27d21-145">Código</span><span class="sxs-lookup"><span data-stu-id="27d21-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="27d21-146">Configuración</span><span class="sxs-lookup"><span data-stu-id="27d21-146">Configuration</span></span>  
 <span data-ttu-id="27d21-147">Se puede usar la configuración siguiente en lugar del código para configurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="27d21-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27d21-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="27d21-148">See Also</span></span>  
 [<span data-ttu-id="27d21-149">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="27d21-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="27d21-150">Seguridad de transporte WS</span><span class="sxs-lookup"><span data-stu-id="27d21-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="27d21-151">Información general sobre la seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="27d21-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="27d21-152">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="27d21-152">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
