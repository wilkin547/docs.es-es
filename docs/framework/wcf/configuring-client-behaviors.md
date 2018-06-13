---
title: Configuración de los comportamientos del cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 062e726b6f1d6831303e1cc0ae82a434daab860c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458112"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="2a5ad-102">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="2a5ad-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="2a5ad-103">Windows Communication Foundation (WCF) configura los comportamientos de dos formas: haciendo referencia a las configuraciones de comportamientos, que se definen en la `<behavior>` sección de un archivo de configuración de aplicación de cliente, o mediante programación en la llamada a aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="2a5ad-104">En este tema se describen ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="2a5ad-105">Al usar un archivo de configuración, la configuración del comportamiento es una colección con nombre de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="2a5ad-106">El nombre de cada configuración de comportamiento debe ser único.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="2a5ad-107">Esta cadena se usa en el atributo `behaviorConfiguration` de una configuración de extremo para vincular el extremo al comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a5ad-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a5ad-108">Example</span></span>  
 <span data-ttu-id="2a5ad-109">El código de configuración siguiente define un comportamiento llamado `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="2a5ad-110">El extremo de cliente hace referencia a este comportamiento en el atributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="2a5ad-111">Uso de comportamientos mediante programación</span><span class="sxs-lookup"><span data-stu-id="2a5ad-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="2a5ad-112">También puede configurar o Insertar comportamientos mediante programación buscando la correspondiente `Behaviors` propiedad en el objeto de cliente de Windows Communication Foundation (WCF) o en el objeto de generador de canal de cliente antes de abrir el cliente.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a5ad-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a5ad-113">Example</span></span>  
 <span data-ttu-id="2a5ad-114">En el ejemplo de código siguiente se muestra cómo insertar un comportamiento mediante programación teniendo acceso a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> en el <xref:System.ServiceModel.Description.ServiceEndpoint> devuelto por la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> antes de la creación del objeto del canal.</span><span class="sxs-lookup"><span data-stu-id="2a5ad-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2a5ad-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a5ad-115">See Also</span></span>  
 [<span data-ttu-id="2a5ad-116">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2a5ad-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
