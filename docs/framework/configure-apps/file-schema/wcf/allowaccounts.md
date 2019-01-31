---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: fd3121146577122446ba82528fc6e46dadbf5033
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255554"
---
# <a name="allowaccounts"></a><span data-ttu-id="11a4f-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="11a4f-101">\<allowAccounts></span></span>
<span data-ttu-id="11a4f-102">Contiene una colección de elementos de configuración que especifique el usuario de cuentas para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="11a4f-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="11a4f-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="11a4f-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a4f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11a4f-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11a4f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="11a4f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="11a4f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="11a4f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11a4f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="11a4f-107">Attributes</span></span>  
 <span data-ttu-id="11a4f-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="11a4f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="11a4f-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="11a4f-109">Child Elements</span></span>  
  
|<span data-ttu-id="11a4f-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="11a4f-110">Attribute</span></span>|<span data-ttu-id="11a4f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a4f-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="11a4f-112">\<add></span><span class="sxs-lookup"><span data-stu-id="11a4f-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="11a4f-113">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido</span><span class="sxs-lookup"><span data-stu-id="11a4f-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11a4f-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="11a4f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="11a4f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="11a4f-115">Element</span></span>|<span data-ttu-id="11a4f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a4f-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11a4f-117">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="11a4f-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="11a4f-118">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="11a4f-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11a4f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a4f-119">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
