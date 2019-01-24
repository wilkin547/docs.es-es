---
title: '&lt;add&gt; de &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670191"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="90878-102">&lt;add&gt; de &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="90878-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="90878-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="90878-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="90878-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90878-104">\<system.serviceModel></span></span>  
<span data-ttu-id="90878-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="90878-105">\<routing></span></span>  
<span data-ttu-id="90878-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="90878-106">\<backupLists></span></span>  
<span data-ttu-id="90878-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="90878-107">\<backupList></span></span>  
<span data-ttu-id="90878-108">\<add></span><span class="sxs-lookup"><span data-stu-id="90878-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90878-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90878-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90878-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="90878-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90878-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="90878-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90878-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="90878-112">Attributes</span></span>  
  
|<span data-ttu-id="90878-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="90878-113">Attribute</span></span>|<span data-ttu-id="90878-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="90878-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90878-115">name</span><span class="sxs-lookup"><span data-stu-id="90878-115">name</span></span>|<span data-ttu-id="90878-116">Cadena que especifica el nombre del punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="90878-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90878-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="90878-117">Child Elements</span></span>  
 <span data-ttu-id="90878-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="90878-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90878-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="90878-119">Parent Elements</span></span>  
  
|<span data-ttu-id="90878-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="90878-120">Element</span></span>|<span data-ttu-id="90878-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="90878-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90878-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="90878-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="90878-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="90878-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90878-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="90878-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
