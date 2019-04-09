---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089541"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="22577-102">\<Agregar > de \<backupList ></span><span class="sxs-lookup"><span data-stu-id="22577-102">\<add> of \<backupList></span></span>
<span data-ttu-id="22577-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="22577-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="22577-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="22577-104">\<system.serviceModel></span></span>  
<span data-ttu-id="22577-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="22577-105">\<routing></span></span>  
<span data-ttu-id="22577-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="22577-106">\<backupLists></span></span>  
<span data-ttu-id="22577-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="22577-107">\<backupList></span></span>  
<span data-ttu-id="22577-108">\<add></span><span class="sxs-lookup"><span data-stu-id="22577-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22577-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22577-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22577-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22577-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22577-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22577-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22577-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="22577-112">Attributes</span></span>  
  
|<span data-ttu-id="22577-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="22577-113">Attribute</span></span>|<span data-ttu-id="22577-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="22577-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22577-115">name</span><span class="sxs-lookup"><span data-stu-id="22577-115">name</span></span>|<span data-ttu-id="22577-116">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="22577-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22577-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22577-117">Child Elements</span></span>  
 <span data-ttu-id="22577-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22577-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22577-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22577-119">Parent Elements</span></span>  
  
|<span data-ttu-id="22577-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="22577-120">Element</span></span>|<span data-ttu-id="22577-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="22577-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22577-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="22577-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="22577-123">Contiene una lista de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="22577-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22577-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="22577-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
