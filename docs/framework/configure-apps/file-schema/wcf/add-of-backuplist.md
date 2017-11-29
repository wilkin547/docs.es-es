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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1475983f7dc54a597198d48a2a404e431ce9c0a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="7ce08-102">&lt;add&gt; de &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="7ce08-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="7ce08-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="7ce08-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="7ce08-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7ce08-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7ce08-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="7ce08-105">\<routing></span></span>  
<span data-ttu-id="7ce08-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="7ce08-106">\<backupLists></span></span>  
<span data-ttu-id="7ce08-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="7ce08-107">\<backupList></span></span>  
<span data-ttu-id="7ce08-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7ce08-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce08-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ce08-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ce08-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ce08-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ce08-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ce08-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ce08-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ce08-112">Attributes</span></span>  
  
|<span data-ttu-id="7ce08-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ce08-113">Attribute</span></span>|<span data-ttu-id="7ce08-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ce08-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ce08-115">name</span><span class="sxs-lookup"><span data-stu-id="7ce08-115">name</span></span>|<span data-ttu-id="7ce08-116">Cadena que especifica el nombre del punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="7ce08-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ce08-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ce08-117">Child Elements</span></span>  
 <span data-ttu-id="7ce08-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7ce08-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ce08-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ce08-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7ce08-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ce08-120">Element</span></span>|<span data-ttu-id="7ce08-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ce08-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ce08-122">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="7ce08-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="7ce08-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="7ce08-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ce08-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ce08-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
