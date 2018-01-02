---
title: '&lt;add&gt; de &lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 786620b0daf1cd22a95f9d0c94b7fc3d17c1a2c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="449fd-102">&lt;add&gt; de &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="449fd-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="449fd-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="449fd-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="449fd-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="449fd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="449fd-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="449fd-105">\<routing></span></span>  
<span data-ttu-id="449fd-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="449fd-106">\<backupLists></span></span>  
<span data-ttu-id="449fd-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="449fd-107">\<backupList></span></span>  
<span data-ttu-id="449fd-108">\<add></span><span class="sxs-lookup"><span data-stu-id="449fd-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="449fd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="449fd-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="449fd-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="449fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="449fd-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="449fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="449fd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="449fd-112">Attributes</span></span>  
  
|<span data-ttu-id="449fd-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="449fd-113">Attribute</span></span>|<span data-ttu-id="449fd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="449fd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="449fd-115">name</span><span class="sxs-lookup"><span data-stu-id="449fd-115">name</span></span>|<span data-ttu-id="449fd-116">Cadena que especifica el nombre del punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="449fd-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="449fd-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="449fd-117">Child Elements</span></span>  
 <span data-ttu-id="449fd-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="449fd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="449fd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="449fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="449fd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="449fd-120">Element</span></span>|<span data-ttu-id="449fd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="449fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="449fd-122">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="449fd-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="449fd-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="449fd-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="449fd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="449fd-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
