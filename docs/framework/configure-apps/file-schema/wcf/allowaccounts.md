---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398405"
---
# \<allowAccounts>
<span data-ttu-id="5279e-101">Contiene una colección de elementos de configuración que especifican las cuentas de usuario para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="5279e-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="5279e-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5279e-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5279e-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5279e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5279e-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5279e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5279e-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="5279e-105">Attributes</span></span>  
 <span data-ttu-id="5279e-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5279e-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5279e-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5279e-107">Child Elements</span></span>  
  
|<span data-ttu-id="5279e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="5279e-108">Attribute</span></span>|<span data-ttu-id="5279e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5279e-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="5279e-110">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="5279e-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5279e-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5279e-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5279e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5279e-112">Element</span></span>|<span data-ttu-id="5279e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5279e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5279e-114">[\<net.pipe>](net-pipe.md)de[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="5279e-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="5279e-115">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="5279e-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5279e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5279e-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
