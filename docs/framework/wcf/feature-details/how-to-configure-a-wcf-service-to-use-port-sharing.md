---
description: Más información acerca de cómo configurar un servicio de Windows Communication Foundation para usar el uso compartido de puertos
title: 'Cómo: Configurar un servicio de Windows Communication Foundation para utilizar puertos compartidos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: 53fe3449ece5a5e545d7add5c4e6c7feebe5a8ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780107"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a><span data-ttu-id="a6787-103">Cómo: Configurar un servicio de Windows Communication Foundation para utilizar puertos compartidos</span><span class="sxs-lookup"><span data-stu-id="a6787-103">How to: Configure a Windows Communication Foundation Service to Use Port Sharing</span></span>

<span data-ttu-id="a6787-104">La manera más sencilla de utilizar el uso compartido de puertos net. TCP://en la aplicación Windows Communication Foundation (WCF) es exponer un servicio mediante <xref:System.ServiceModel.NetTcpBinding> .</span><span class="sxs-lookup"><span data-stu-id="a6787-104">The easiest way to use net.tcp:// port sharing in your Windows Communication Foundation (WCF) application is to expose a service using the <xref:System.ServiceModel.NetTcpBinding>.</span></span>  
  
 <span data-ttu-id="a6787-105">Este enlace proporciona una propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> que controla si la compartición de puertos de net.tcp:// está habilitada para el servicio que se está configurando con este enlace.</span><span class="sxs-lookup"><span data-stu-id="a6787-105">This binding provides a <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property that controls whether net.tcp:// port sharing is enabled for the service being configured with this binding.</span></span>  
  
 <span data-ttu-id="a6787-106">El siguiente procedimiento muestra cómo utilizar la clase <xref:System.ServiceModel.NetTcpBinding> para abrir un punto de conexión en el URI net.tcp://localhost/MyService, primero mediante código y, a continuación, mediante los elementos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6787-106">The following procedure shows how to use the <xref:System.ServiceModel.NetTcpBinding> class to open an endpoint at the Uniform Resource Identifier (URI) net.tcp://localhost/MyService, first in code and then by using configuration elements.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a><span data-ttu-id="a6787-107">Para habilitar la compartición de puertos de net.tcp:// en un NetTcpBinding mediante código</span><span class="sxs-lookup"><span data-stu-id="a6787-107">To enable net.tcp:// port sharing on a NetTcpBinding in code</span></span>  
  
1. <span data-ttu-id="a6787-108">Cree un servicio para implementar un contrato llamado `IMyService` y llámelo `MyService` .</span><span class="sxs-lookup"><span data-stu-id="a6787-108">Create a service to implement a contract called `IMyService` and call it `MyService`, .</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2. <span data-ttu-id="a6787-109">Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="a6787-109">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3. <span data-ttu-id="a6787-110">Cree un <xref:System.ServiceModel.ServiceHost> y agregue el punto de conexión de servicio a él para `MyService` que utiliza el <xref:System.ServiceModel.NetTcpBinding> con uso compartido de puerto habilitado y que realiza escuchas en el URI de la dirección del punto de conexión "net.tcp://localhost/MyService".</span><span class="sxs-lookup"><span data-stu-id="a6787-110">Create a <xref:System.ServiceModel.ServiceHost> and add the service endpoint to it for `MyService` that uses the port sharing-enabled <xref:System.ServiceModel.NetTcpBinding> and that listens at the endpoint address URI "net.tcp://localhost/MyService".</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    > <span data-ttu-id="a6787-111">Este ejemplo utiliza el puerto TCP predeterminado 808, porque el URI de dirección de punto de conexión no especifica un número de puerto diferente.</span><span class="sxs-lookup"><span data-stu-id="a6787-111">This example uses the default TCP port of 808 because the endpoint address URI does not specify a different port number.</span></span> <span data-ttu-id="a6787-112">Dado que el uso compartido del puerto está habilitado explícitamente en el enlace de transporte, este servicio puede compartir el puerto 808 con otros servicios en otros procesos.</span><span class="sxs-lookup"><span data-stu-id="a6787-112">Because port sharing is explicitly enabled on the transport binding, this service can share port 808 with other services in other processes.</span></span> <span data-ttu-id="a6787-113">Si no se permitiera el uso compartido del puerto y otra aplicación ya estuviese utilizando el puerto 808, este servicio produciría una <xref:System.ServiceModel.AddressAlreadyInUseException> al abrirse.</span><span class="sxs-lookup"><span data-stu-id="a6787-113">If port sharing were not allowed and another application were already using port 808, this service would throw an <xref:System.ServiceModel.AddressAlreadyInUseException> when it was opened.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a><span data-ttu-id="a6787-114">Para habilitar el uso compartido de puerto de  net.tcp:// en un NetTcpBinding mediante configuración</span><span class="sxs-lookup"><span data-stu-id="a6787-114">To enable net.tcp:// port sharing on a NetTcpBinding in configuration</span></span>  
  
1. <span data-ttu-id="a6787-115">El ejemplo siguiente muestra cómo habilitar el uso compartido de puerto y agregar el punto de conexión de servicio mediante elementos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6787-115">The following example shows how to enable port sharing and add the service endpoint using configuration elements.</span></span>  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6787-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6787-116">See also</span></span>

- [<span data-ttu-id="a6787-117">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a6787-117">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="a6787-118">Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a6787-118">How to: Enable the Net.TCP Port Sharing Service</span></span>](how-to-enable-the-net-tcp-port-sharing-service.md)
