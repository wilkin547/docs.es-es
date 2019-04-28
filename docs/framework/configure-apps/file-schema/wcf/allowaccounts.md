---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673542"
---
# <a name="allowaccounts"></a><span data-ttu-id="ec0e2-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="ec0e2-101">\<allowAccounts></span></span>
<span data-ttu-id="ec0e2-102">Contiene una colección de elementos de configuración que especifique el usuario de cuentas para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="ec0e2-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ec0e2-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec0e2-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec0e2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ec0e2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ec0e2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec0e2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec0e2-107">Attributes</span></span>  
 <span data-ttu-id="ec0e2-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec0e2-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec0e2-109">Child Elements</span></span>  
  
|<span data-ttu-id="ec0e2-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ec0e2-110">Attribute</span></span>|<span data-ttu-id="ec0e2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0e2-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ec0e2-112">\<add></span><span class="sxs-lookup"><span data-stu-id="ec0e2-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="ec0e2-113">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido</span><span class="sxs-lookup"><span data-stu-id="ec0e2-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec0e2-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ec0e2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ec0e2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec0e2-115">Element</span></span>|<span data-ttu-id="ec0e2-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0e2-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec0e2-117">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="ec0e2-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="ec0e2-118">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec0e2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec0e2-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
