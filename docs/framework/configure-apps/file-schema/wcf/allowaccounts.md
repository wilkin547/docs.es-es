---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 3432d33c0cd65af03d2b1ac1302ca2c8ff3e0f43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201647"
---
# \<allowAccounts>

<span data-ttu-id="dd436-101">Contiene una colección de elementos de configuración que especifican las cuentas de usuario para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="dd436-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="dd436-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd436-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd436-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dd436-103">Attributes and Elements</span></span>  

 <span data-ttu-id="dd436-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dd436-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd436-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd436-105">Attributes</span></span>  

 <span data-ttu-id="dd436-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dd436-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd436-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dd436-107">Child Elements</span></span>  
  
|<span data-ttu-id="dd436-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="dd436-108">Attribute</span></span>|<span data-ttu-id="dd436-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd436-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="dd436-110">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="dd436-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd436-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dd436-111">Parent Elements</span></span>  
  
|<span data-ttu-id="dd436-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd436-112">Element</span></span>|<span data-ttu-id="dd436-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd436-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd436-114">[\<net.pipe>](net-pipe.md) o [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="dd436-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="dd436-115">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="dd436-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd436-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd436-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
