---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: e61ee275a7e98f13370504f5f15fdbe62a8221bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285797"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="6ff3c-102">\<Agregar > de \<backupList ></span><span class="sxs-lookup"><span data-stu-id="6ff3c-102">\<add> of \<backupList></span></span>
<span data-ttu-id="6ff3c-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="6ff3c-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="6ff3c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6ff3c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6ff3c-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="6ff3c-105">\<routing></span></span>  
<span data-ttu-id="6ff3c-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="6ff3c-106">\<backupLists></span></span>  
<span data-ttu-id="6ff3c-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="6ff3c-107">\<backupList></span></span>  
<span data-ttu-id="6ff3c-108">\<add></span><span class="sxs-lookup"><span data-stu-id="6ff3c-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff3c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ff3c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ff3c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ff3c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6ff3c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ff3c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ff3c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ff3c-112">Attributes</span></span>  
  
|<span data-ttu-id="6ff3c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ff3c-113">Attribute</span></span>|<span data-ttu-id="6ff3c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ff3c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ff3c-115">name</span><span class="sxs-lookup"><span data-stu-id="6ff3c-115">name</span></span>|<span data-ttu-id="6ff3c-116">Cadena que especifica el nombre del punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="6ff3c-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ff3c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ff3c-117">Child Elements</span></span>  
 <span data-ttu-id="6ff3c-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ff3c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ff3c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ff3c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6ff3c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ff3c-120">Element</span></span>|<span data-ttu-id="6ff3c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ff3c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ff3c-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="6ff3c-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6ff3c-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="6ff3c-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ff3c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ff3c-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
