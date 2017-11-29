---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="dacd6-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="dacd6-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="dacd6-103">Contiene una colección de elementos de configuración que especifica las cuentas de usuario para los procesos que hospedan servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] y se concede el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="dacd6-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="dacd6-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="dacd6-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dacd6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dacd6-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dacd6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dacd6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="dacd6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dacd6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dacd6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="dacd6-108">Attributes</span></span>  
 <span data-ttu-id="dacd6-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dacd6-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dacd6-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dacd6-110">Child Elements</span></span>  
  
|<span data-ttu-id="dacd6-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="dacd6-111">Attribute</span></span>|<span data-ttu-id="dacd6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="dacd6-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="dacd6-113">\<add></span><span class="sxs-lookup"><span data-stu-id="dacd6-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="dacd6-114">Agrega una cuenta de usuario para los procesos que hospedan los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="dacd6-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dacd6-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dacd6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="dacd6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="dacd6-116">Element</span></span>|<span data-ttu-id="dacd6-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="dacd6-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dacd6-118">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="dacd6-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="dacd6-119">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="dacd6-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dacd6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dacd6-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
