---
title: Seguridad de transporte con autenticación básica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: eace5ce9a84d99cb2526896cca36a9e2a13fd5f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742695"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="5ddc1-102">Seguridad de transporte con autenticación básica</span><span class="sxs-lookup"><span data-stu-id="5ddc1-102">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="5ddc1-103">En la ilustración siguiente se muestra un servicio y un cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5ddc1-103">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="5ddc1-104">El servidor necesita un certificado X.509 válido que se puede utilizar para Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-104">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="5ddc1-105">Además, el servicio web ya tiene una implementación SSL que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-105">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="5ddc1-106">Para obtener más información sobre cómo habilitar la autenticación básica en Internet Information Services (IIS), vea <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-106">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![Captura de pantalla que muestra la seguridad de transporte con autenticación básica.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="5ddc1-108">Característica</span><span class="sxs-lookup"><span data-stu-id="5ddc1-108">Characteristic</span></span>|<span data-ttu-id="5ddc1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ddc1-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5ddc1-110">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="5ddc1-110">Security Mode</span></span>|<span data-ttu-id="5ddc1-111">Transport</span><span class="sxs-lookup"><span data-stu-id="5ddc1-111">Transport</span></span>|  
|<span data-ttu-id="5ddc1-112">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="5ddc1-112">Interoperability</span></span>|<span data-ttu-id="5ddc1-113">Con clientes de servicios Web existentes y servicios</span><span class="sxs-lookup"><span data-stu-id="5ddc1-113">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="5ddc1-114">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="5ddc1-114">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="5ddc1-115">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="5ddc1-115">Authentication (Client)</span></span>|<span data-ttu-id="5ddc1-116">Sí (utilizar HTTPS)</span><span class="sxs-lookup"><span data-stu-id="5ddc1-116">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="5ddc1-117">Sí (a través del nombre de usuario/Contraseña)</span><span class="sxs-lookup"><span data-stu-id="5ddc1-117">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="5ddc1-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="5ddc1-118">Integrity</span></span>|<span data-ttu-id="5ddc1-119">Sí</span><span class="sxs-lookup"><span data-stu-id="5ddc1-119">Yes</span></span>|  
|<span data-ttu-id="5ddc1-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="5ddc1-120">Confidentiality</span></span>|<span data-ttu-id="5ddc1-121">Sí</span><span class="sxs-lookup"><span data-stu-id="5ddc1-121">Yes</span></span>|  
|<span data-ttu-id="5ddc1-122">Transport</span><span class="sxs-lookup"><span data-stu-id="5ddc1-122">Transport</span></span>|<span data-ttu-id="5ddc1-123">HTTPS</span><span class="sxs-lookup"><span data-stu-id="5ddc1-123">HTTPS</span></span>|  
|<span data-ttu-id="5ddc1-124">Enlace</span><span class="sxs-lookup"><span data-stu-id="5ddc1-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="5ddc1-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="5ddc1-125">Service</span></span>  
 <span data-ttu-id="5ddc1-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5ddc1-127">Siga uno de los procedimientos que se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="5ddc1-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="5ddc1-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="5ddc1-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5ddc1-130">Código</span><span class="sxs-lookup"><span data-stu-id="5ddc1-130">Code</span></span>  
 <span data-ttu-id="5ddc1-131">El código siguiente muestra cómo crear un extremo de servicio que utiliza un nombre de usuario del dominio de Windows y contraseña para la seguridad de la transferencia.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-131">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="5ddc1-132">Tenga en cuenta que el servicio exige un certificado X.509 que autentique al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-132">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="5ddc1-133">Para obtener más información, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="5ddc1-133">For more information, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="5ddc1-134">Configuración de</span><span class="sxs-lookup"><span data-stu-id="5ddc1-134">Configuration</span></span>  
 <span data-ttu-id="5ddc1-135">Lo siguiente configura un servicio para utilizar la autenticación básica con seguridad de nivel de transporte:</span><span class="sxs-lookup"><span data-stu-id="5ddc1-135">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"   
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"   
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="5ddc1-136">Client</span><span class="sxs-lookup"><span data-stu-id="5ddc1-136">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="5ddc1-137">Código</span><span class="sxs-lookup"><span data-stu-id="5ddc1-137">Code</span></span>  
 <span data-ttu-id="5ddc1-138">El código siguiente muestra el código de cliente que incluye el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-138">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="5ddc1-139">Tenga en cuenta que el usuario debe proporcionar un nombre de usuario de Windows válido y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-139">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="5ddc1-140">El código para devolver el nombre de usuario y la contraseña no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-140">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="5ddc1-141">Utilice un cuadro de diálogo u otra interfaz para solicitar la información al usuario.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-141">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ddc1-142">El nombre de usuario y contraseña solo se pueden establecer utilizando el código.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-142">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="5ddc1-143">Configuración de</span><span class="sxs-lookup"><span data-stu-id="5ddc1-143">Configuration</span></span>  
 <span data-ttu-id="5ddc1-144">El código siguiente muestra la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-144">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ddc1-145">No puede utilizar la configuración para establecer el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-145">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="5ddc1-146">La configuración mostrada aquí se debe aumentar utilizando el código para establecer el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5ddc1-146">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
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
  
## <a name="see-also"></a><span data-ttu-id="5ddc1-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ddc1-147">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="5ddc1-148">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5ddc1-148">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5ddc1-149">Configuración de un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="5ddc1-149">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="5ddc1-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="5ddc1-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="5ddc1-151">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5ddc1-151">\<clientCredentials></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="5ddc1-152">[Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5ddc1-152">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
