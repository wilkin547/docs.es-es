---
title: Configuración de los comportamientos del cliente
description: 'Obtenga información sobre las dos formas en que WCF configura los comportamientos: en el archivo de configuración de la aplicación o mediante programación desde la aplicación que realiza la llamada.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 4b83862221cf249455478c3ade159a3101062f3e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245445"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="ce16e-103">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="ce16e-103">Configuring Client Behaviors</span></span>
<span data-ttu-id="ce16e-104">Windows Communication Foundation (WCF) configura los comportamientos de dos maneras: mediante la referencia a las configuraciones de comportamiento, que se definen en la `<behavior>` sección de un archivo de configuración de la aplicación cliente, o mediante programación en la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce16e-104">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="ce16e-105">En este tema se describen ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="ce16e-105">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="ce16e-106">Al usar un archivo de configuración, la configuración del comportamiento es una colección con nombre de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="ce16e-106">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="ce16e-107">El nombre de cada configuración de comportamiento debe ser único.</span><span class="sxs-lookup"><span data-stu-id="ce16e-107">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="ce16e-108">Esta cadena se usa en el atributo `behaviorConfiguration` de una configuración de punto de conexión para vincular el punto de conexión al comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ce16e-108">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce16e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce16e-109">Example</span></span>  
 <span data-ttu-id="ce16e-110">El código de configuración siguiente define un comportamiento llamado `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="ce16e-110">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="ce16e-111">El punto de conexión de cliente hace referencia a este comportamiento en el atributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="ce16e-111">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="ce16e-112">Uso de comportamientos mediante programación</span><span class="sxs-lookup"><span data-stu-id="ce16e-112">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="ce16e-113">También puede configurar o insertar comportamientos mediante programación localizando la `Behaviors` propiedad adecuada en el objeto de cliente Windows Communication Foundation (WCF) o en el objeto de generador de canales de cliente antes de abrir el cliente.</span><span class="sxs-lookup"><span data-stu-id="ce16e-113">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce16e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce16e-114">Example</span></span>  
 <span data-ttu-id="ce16e-115">En el ejemplo de código siguiente se muestra cómo insertar un comportamiento mediante programación teniendo acceso a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> en el <xref:System.ServiceModel.Description.ServiceEndpoint> devuelto por la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> antes de la creación del objeto del canal.</span><span class="sxs-lookup"><span data-stu-id="ce16e-115">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="ce16e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce16e-116">See also</span></span>

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
