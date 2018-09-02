---
title: Seguridad del transporte con clientes anónimos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3acea654cc84ede4b264c2db3ae6e9d042f4f5cb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418388"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="fc475-102">Seguridad del transporte con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="fc475-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="fc475-103">Este escenario Windows Communication Foundation (WCF) utiliza la seguridad de transporte (HTTPS) para garantizar la confidencialidad e integridad.</span><span class="sxs-lookup"><span data-stu-id="fc475-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="fc475-104">El servidor debe autenticarse con un certificado de Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="fc475-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="fc475-105">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="fc475-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="fc475-106">Para una aplicación de ejemplo, vea [seguridad de transporte WS](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="fc475-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> <span data-ttu-id="fc475-107">Para obtener más información acerca de la seguridad de transporte, vea [información general sobre la seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fc475-107">For more information about transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 <span data-ttu-id="fc475-108">Para obtener más información sobre el uso de un certificado con un servicio, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="fc475-108">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="fc475-109">![Mediante la seguridad de transporte con clientes anónimos](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="fc475-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="fc475-110">Característica</span><span class="sxs-lookup"><span data-stu-id="fc475-110">Characteristic</span></span>|<span data-ttu-id="fc475-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc475-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fc475-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="fc475-112">Security Mode</span></span>|<span data-ttu-id="fc475-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="fc475-113">Transport</span></span>|  
|<span data-ttu-id="fc475-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="fc475-114">Interoperability</span></span>|<span data-ttu-id="fc475-115">Con servicios y clientes Web existentes</span><span class="sxs-lookup"><span data-stu-id="fc475-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="fc475-116">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="fc475-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="fc475-117">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="fc475-117">Authentication (Client)</span></span>|<span data-ttu-id="fc475-118">Sí</span><span class="sxs-lookup"><span data-stu-id="fc475-118">Yes</span></span><br /><br /> <span data-ttu-id="fc475-119">Nivel de aplicación (no hay compatibilidad WCF)</span><span class="sxs-lookup"><span data-stu-id="fc475-119">Application level (no WCF support)</span></span>|  
|<span data-ttu-id="fc475-120">Integridad</span><span class="sxs-lookup"><span data-stu-id="fc475-120">Integrity</span></span>|<span data-ttu-id="fc475-121">Sí</span><span class="sxs-lookup"><span data-stu-id="fc475-121">Yes</span></span>|  
|<span data-ttu-id="fc475-122">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="fc475-122">Confidentiality</span></span>|<span data-ttu-id="fc475-123">Sí</span><span class="sxs-lookup"><span data-stu-id="fc475-123">Yes</span></span>|  
|<span data-ttu-id="fc475-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="fc475-124">Transport</span></span>|<span data-ttu-id="fc475-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fc475-125">HTTPS</span></span>|  
|<span data-ttu-id="fc475-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fc475-126">Binding</span></span>|<span data-ttu-id="fc475-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="fc475-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="fc475-128">web de Office</span><span class="sxs-lookup"><span data-stu-id="fc475-128">Service</span></span>  
 <span data-ttu-id="fc475-129">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="fc475-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fc475-130">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fc475-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fc475-131">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="fc475-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="fc475-132">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="fc475-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fc475-133">Código</span><span class="sxs-lookup"><span data-stu-id="fc475-133">Code</span></span>  
 <span data-ttu-id="fc475-134">El código siguiente muestra cómo crear un punto de conexión mediante la seguridad del transporte:</span><span class="sxs-lookup"><span data-stu-id="fc475-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="fc475-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="fc475-135">Configuration</span></span>  
 <span data-ttu-id="fc475-136">El código siguiente configura el mismo punto de conexión mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="fc475-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="fc475-137">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="fc475-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="fc475-138">Cliente</span><span class="sxs-lookup"><span data-stu-id="fc475-138">Client</span></span>  
 <span data-ttu-id="fc475-139">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="fc475-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fc475-140">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fc475-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fc475-141">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="fc475-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="fc475-142">Cree un cliente que no defina direcciones de extremo.</span><span class="sxs-lookup"><span data-stu-id="fc475-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="fc475-143">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="fc475-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="fc475-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc475-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="fc475-145">Código</span><span class="sxs-lookup"><span data-stu-id="fc475-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="fc475-146">Configuración</span><span class="sxs-lookup"><span data-stu-id="fc475-146">Configuration</span></span>  
 <span data-ttu-id="fc475-147">Se puede usar la configuración siguiente en lugar del código para configurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="fc475-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc475-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc475-148">See Also</span></span>  
 [<span data-ttu-id="fc475-149">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="fc475-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="fc475-150">Seguridad de transporte WS</span><span class="sxs-lookup"><span data-stu-id="fc475-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="fc475-151">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="fc475-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="fc475-152">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="fc475-152">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
