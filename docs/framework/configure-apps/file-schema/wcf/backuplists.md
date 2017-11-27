---
title: '&lt;backupLists&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f63dbad93fb36eab1b44c3f4135be3530ebdf340
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="15234-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="15234-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="15234-103">Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.</span><span class="sxs-lookup"><span data-stu-id="15234-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="15234-104">Cada elemento secundario es una lista auxiliar que enumera un conjunto de extremos que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="15234-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="15234-105">Si el primer punto de conexión en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="15234-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="15234-106">De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.</span><span class="sxs-lookup"><span data-stu-id="15234-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="15234-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="15234-107">\<system.serviceModel></span></span>  
<span data-ttu-id="15234-108">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="15234-108">\<routing></span></span>  
<span data-ttu-id="15234-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="15234-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15234-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15234-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15234-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15234-111">Attributes and Elements</span></span>  
 <span data-ttu-id="15234-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15234-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15234-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="15234-113">Attributes</span></span>  
 <span data-ttu-id="15234-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15234-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15234-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15234-115">Child Elements</span></span>  
  
|<span data-ttu-id="15234-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="15234-116">Element</span></span>|<span data-ttu-id="15234-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="15234-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15234-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="15234-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="15234-119">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="15234-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="15234-120">.</span><span class="sxs-lookup"><span data-stu-id="15234-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15234-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15234-121">Parent Elements</span></span>  
  
|<span data-ttu-id="15234-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="15234-122">Element</span></span>|<span data-ttu-id="15234-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="15234-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15234-124">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="15234-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="15234-125">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="15234-125">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15234-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="15234-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
