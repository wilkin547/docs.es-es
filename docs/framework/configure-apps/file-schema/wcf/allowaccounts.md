---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 097112a8b54467843554047882e55b62d7813c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352882"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="a7fee-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="a7fee-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="a7fee-103">Contiene una colección de elementos de configuración especificada por el usuario cuentas para los procesos que hospedan servicios Windows Communication Foundation (WCF) y se concede el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="a7fee-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="a7fee-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="a7fee-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7fee-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7fee-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7fee-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a7fee-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7fee-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7fee-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7fee-108">Attributes</span></span>  
 <span data-ttu-id="a7fee-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7fee-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7fee-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7fee-110">Child Elements</span></span>  
  
|<span data-ttu-id="a7fee-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7fee-111">Attribute</span></span>|<span data-ttu-id="a7fee-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7fee-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a7fee-113">\<add></span><span class="sxs-lookup"><span data-stu-id="a7fee-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="a7fee-114">Agrega una cuenta de usuario para los procesos que alojan servicios WCF y se concede el acceso de conexión al servicio de uso compartido</span><span class="sxs-lookup"><span data-stu-id="a7fee-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7fee-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7fee-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a7fee-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7fee-116">Element</span></span>|<span data-ttu-id="a7fee-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7fee-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7fee-118">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="a7fee-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="a7fee-119">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="a7fee-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7fee-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7fee-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
