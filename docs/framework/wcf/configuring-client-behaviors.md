---
title: Configuración de los comportamientos del cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193660"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="a1dd1-102">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="a1dd1-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="a1dd1-103">Windows Communication Foundation (WCF) configura los comportamientos de dos formas: haciendo referencia a las configuraciones de comportamiento, que se definen en el `<behavior>` sección de un archivo de configuración de aplicación de cliente, o mediante programación en la llamada a aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="a1dd1-104">En este tema se describen ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="a1dd1-105">Al usar un archivo de configuración, la configuración del comportamiento es una colección con nombre de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="a1dd1-106">El nombre de cada configuración de comportamiento debe ser único.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="a1dd1-107">Esta cadena se usa en el atributo `behaviorConfiguration` de una configuración de punto de conexión para vincular el punto de conexión al comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1dd1-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1dd1-108">Example</span></span>  
 <span data-ttu-id="a1dd1-109">El código de configuración siguiente define un comportamiento llamado `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="a1dd1-110">El punto de conexión de cliente hace referencia a este comportamiento en el atributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="a1dd1-111">Uso de comportamientos mediante programación</span><span class="sxs-lookup"><span data-stu-id="a1dd1-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="a1dd1-112">También puede configurar o Insertar comportamientos mediante programación ubicando adecuado `Behaviors` propiedad en el objeto de cliente de Windows Communication Foundation (WCF) o en el objeto de generador del canal de cliente antes de abrir el cliente.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1dd1-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1dd1-113">Example</span></span>  
 <span data-ttu-id="a1dd1-114">En el ejemplo de código siguiente se muestra cómo insertar un comportamiento mediante programación teniendo acceso a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> en el <xref:System.ServiceModel.Description.ServiceEndpoint> devuelto por la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> antes de la creación del objeto del canal.</span><span class="sxs-lookup"><span data-stu-id="a1dd1-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a1dd1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1dd1-115">See also</span></span>

- [<span data-ttu-id="a1dd1-116">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a1dd1-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
