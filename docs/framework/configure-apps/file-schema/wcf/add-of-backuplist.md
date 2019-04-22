---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089541"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="104d1-102">\<Agregar > de \<backupList ></span><span class="sxs-lookup"><span data-stu-id="104d1-102">\<add> of \<backupList></span></span>
<span data-ttu-id="104d1-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="104d1-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="104d1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="104d1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="104d1-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="104d1-105">\<routing></span></span>  
<span data-ttu-id="104d1-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="104d1-106">\<backupLists></span></span>  
<span data-ttu-id="104d1-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="104d1-107">\<backupList></span></span>  
<span data-ttu-id="104d1-108">\<add></span><span class="sxs-lookup"><span data-stu-id="104d1-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104d1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="104d1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="104d1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="104d1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="104d1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="104d1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="104d1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="104d1-112">Attributes</span></span>  
  
|<span data-ttu-id="104d1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="104d1-113">Attribute</span></span>|<span data-ttu-id="104d1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="104d1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="104d1-115">name</span><span class="sxs-lookup"><span data-stu-id="104d1-115">name</span></span>|<span data-ttu-id="104d1-116">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="104d1-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="104d1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="104d1-117">Child Elements</span></span>  
 <span data-ttu-id="104d1-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="104d1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="104d1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="104d1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="104d1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="104d1-120">Element</span></span>|<span data-ttu-id="104d1-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="104d1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="104d1-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="104d1-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="104d1-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="104d1-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="104d1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="104d1-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
