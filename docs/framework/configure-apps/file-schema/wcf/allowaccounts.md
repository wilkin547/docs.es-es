---
description: 'Más información acerca de: <allowAccounts>'
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 5211d694e5318faf0cfc31b404764acb405bd096
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749992"
---
# \<allowAccounts>

<span data-ttu-id="42a16-102">Contiene una colección de elementos de configuración que especifican las cuentas de usuario para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="42a16-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="42a16-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42a16-103">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42a16-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42a16-104">Attributes and Elements</span></span>  

 <span data-ttu-id="42a16-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42a16-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42a16-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="42a16-106">Attributes</span></span>  

 <span data-ttu-id="42a16-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="42a16-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42a16-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42a16-108">Child Elements</span></span>  
  
|<span data-ttu-id="42a16-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="42a16-109">Attribute</span></span>|<span data-ttu-id="42a16-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="42a16-110">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="42a16-111">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="42a16-111">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42a16-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42a16-112">Parent Elements</span></span>  
  
|<span data-ttu-id="42a16-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="42a16-113">Element</span></span>|<span data-ttu-id="42a16-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="42a16-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42a16-115">[\<net.pipe>](net-pipe.md) o [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="42a16-115">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="42a16-116">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="42a16-116">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42a16-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a16-117">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
