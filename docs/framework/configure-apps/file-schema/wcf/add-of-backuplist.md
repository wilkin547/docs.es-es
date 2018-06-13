---
title: '&lt;add&gt; de &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 7e7361b24c0444b5f3d51a6f5bf079d5eb2dee18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745557"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="a7bd1-102">&lt;add&gt; de &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="a7bd1-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="a7bd1-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="a7bd1-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="a7bd1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7bd1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a7bd1-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="a7bd1-105">\<routing></span></span>  
<span data-ttu-id="a7bd1-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="a7bd1-106">\<backupLists></span></span>  
<span data-ttu-id="a7bd1-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="a7bd1-107">\<backupList></span></span>  
<span data-ttu-id="a7bd1-108">\<add></span><span class="sxs-lookup"><span data-stu-id="a7bd1-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bd1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7bd1-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7bd1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7bd1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a7bd1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7bd1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7bd1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7bd1-112">Attributes</span></span>  
  
|<span data-ttu-id="a7bd1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7bd1-113">Attribute</span></span>|<span data-ttu-id="a7bd1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7bd1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7bd1-115">name</span><span class="sxs-lookup"><span data-stu-id="a7bd1-115">name</span></span>|<span data-ttu-id="a7bd1-116">Cadena que especifica el nombre del punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a7bd1-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7bd1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7bd1-117">Child Elements</span></span>  
 <span data-ttu-id="a7bd1-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7bd1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7bd1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7bd1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a7bd1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7bd1-120">Element</span></span>|<span data-ttu-id="a7bd1-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7bd1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7bd1-122">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="a7bd1-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a7bd1-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento para usar en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="a7bd1-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7bd1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7bd1-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
