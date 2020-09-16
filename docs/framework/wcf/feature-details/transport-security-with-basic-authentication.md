---
title: Seguridad de transporte con autenticación básica
description: Revise este escenario de WCF, que muestra la autenticación básica para un servicio y un cliente WCF. El servicio necesita un certificado válido en el que el cliente confíe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: 2add8c21ca8ade4b530e0e6b1b3c5bba66e100ab
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556790"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="30147-104">Seguridad de transporte con autenticación básica</span><span class="sxs-lookup"><span data-stu-id="30147-104">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="30147-105">En la ilustración siguiente se muestra un servicio y un cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="30147-105">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="30147-106">El servidor necesita un certificado X.509 válido que se puede utilizar para Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="30147-106">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="30147-107">Además, el servicio web ya tiene una implementación SSL que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="30147-107">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="30147-108">Para obtener más información acerca de cómo habilitar la autenticación básica en Internet Information Services (IIS), vea <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication> .</span><span class="sxs-lookup"><span data-stu-id="30147-108">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![Captura de pantalla que muestra la seguridad de transporte con autenticación básica.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="30147-110">Característica</span><span class="sxs-lookup"><span data-stu-id="30147-110">Characteristic</span></span>|<span data-ttu-id="30147-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="30147-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="30147-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="30147-112">Security Mode</span></span>|<span data-ttu-id="30147-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="30147-113">Transport</span></span>|  
|<span data-ttu-id="30147-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="30147-114">Interoperability</span></span>|<span data-ttu-id="30147-115">Con clientes de servicios Web existentes y servicios</span><span class="sxs-lookup"><span data-stu-id="30147-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="30147-116">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="30147-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="30147-117">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="30147-117">Authentication (Client)</span></span>|<span data-ttu-id="30147-118">Sí (utilizar HTTPS)</span><span class="sxs-lookup"><span data-stu-id="30147-118">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="30147-119">Sí (a través del nombre de usuario/Contraseña)</span><span class="sxs-lookup"><span data-stu-id="30147-119">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="30147-120">Integridad</span><span class="sxs-lookup"><span data-stu-id="30147-120">Integrity</span></span>|<span data-ttu-id="30147-121">Sí</span><span class="sxs-lookup"><span data-stu-id="30147-121">Yes</span></span>|  
|<span data-ttu-id="30147-122">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="30147-122">Confidentiality</span></span>|<span data-ttu-id="30147-123">Sí</span><span class="sxs-lookup"><span data-stu-id="30147-123">Yes</span></span>|  
|<span data-ttu-id="30147-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="30147-124">Transport</span></span>|<span data-ttu-id="30147-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="30147-125">HTTPS</span></span>|  
|<span data-ttu-id="30147-126">Enlace</span><span class="sxs-lookup"><span data-stu-id="30147-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="30147-127">Servicio</span><span class="sxs-lookup"><span data-stu-id="30147-127">Service</span></span>  
 <span data-ttu-id="30147-128">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="30147-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="30147-129">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="30147-129">Do one of the following:</span></span>  
  
- <span data-ttu-id="30147-130">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="30147-130">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="30147-131">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="30147-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="30147-132">Código</span><span class="sxs-lookup"><span data-stu-id="30147-132">Code</span></span>  
 <span data-ttu-id="30147-133">El código siguiente muestra cómo crear un extremo de servicio que utiliza un nombre de usuario del dominio de Windows y contraseña para la seguridad de la transferencia.</span><span class="sxs-lookup"><span data-stu-id="30147-133">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="30147-134">Tenga en cuenta que el servicio exige un certificado X.509 que autentique al cliente.</span><span class="sxs-lookup"><span data-stu-id="30147-134">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="30147-135">Para obtener más información, consulte [trabajar con certificados](working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="30147-135">For more information, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="30147-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="30147-136">Configuration</span></span>  
 <span data-ttu-id="30147-137">Lo siguiente configura un servicio para utilizar la autenticación básica con seguridad de nivel de transporte:</span><span class="sxs-lookup"><span data-stu-id="30147-137">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="30147-138">Cliente</span><span class="sxs-lookup"><span data-stu-id="30147-138">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="30147-139">Código</span><span class="sxs-lookup"><span data-stu-id="30147-139">Code</span></span>  
 <span data-ttu-id="30147-140">El código siguiente muestra el código de cliente que incluye el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="30147-140">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="30147-141">Tenga en cuenta que el usuario debe proporcionar un nombre de usuario de Windows válido y contraseña.</span><span class="sxs-lookup"><span data-stu-id="30147-141">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="30147-142">El código para devolver el nombre de usuario y la contraseña no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="30147-142">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="30147-143">Utilice un cuadro de diálogo u otra interfaz para solicitar la información al usuario.</span><span class="sxs-lookup"><span data-stu-id="30147-143">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30147-144">El nombre de usuario y contraseña solo se pueden establecer utilizando el código.</span><span class="sxs-lookup"><span data-stu-id="30147-144">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="30147-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="30147-145">Configuration</span></span>  
 <span data-ttu-id="30147-146">El código siguiente muestra la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="30147-146">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30147-147">No puede utilizar la configuración para establecer el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="30147-147">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="30147-148">La configuración mostrada aquí se debe aumentar utilizando el código para establecer el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="30147-148">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30147-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="30147-149">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="30147-150">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="30147-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="30147-151">Procedimiento para configurar un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="30147-151">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="30147-152">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="30147-152">Security Overview</span></span>](security-overview.md)
- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="30147-153">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="30147-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
