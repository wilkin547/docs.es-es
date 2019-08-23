---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926596"
---
# <a name="allowaccounts"></a><span data-ttu-id="23207-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="23207-101">\<allowAccounts></span></span>
<span data-ttu-id="23207-102">Contiene una colección de elementos de configuración que especifican las cuentas de usuario para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="23207-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="23207-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="23207-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23207-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23207-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23207-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="23207-105">Attributes and Elements</span></span>  
 <span data-ttu-id="23207-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="23207-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23207-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="23207-107">Attributes</span></span>  
 <span data-ttu-id="23207-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="23207-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23207-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="23207-109">Child Elements</span></span>  
  
|<span data-ttu-id="23207-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="23207-110">Attribute</span></span>|<span data-ttu-id="23207-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="23207-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="23207-112">\<add></span><span class="sxs-lookup"><span data-stu-id="23207-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="23207-113">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="23207-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23207-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="23207-114">Parent Elements</span></span>  
  
|<span data-ttu-id="23207-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="23207-115">Element</span></span>|<span data-ttu-id="23207-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="23207-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23207-117">net. Pipe > o [ \<](net-pipe.md) [ \<net. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="23207-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="23207-118">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="23207-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23207-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="23207-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
