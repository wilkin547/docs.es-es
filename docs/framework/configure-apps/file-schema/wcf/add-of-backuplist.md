---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663370"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="b13e4-102">\<Agregar > de \<backupList ></span><span class="sxs-lookup"><span data-stu-id="b13e4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="b13e4-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="b13e4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="b13e4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b13e4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b13e4-105">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="b13e4-105">\<routing></span></span>  
<span data-ttu-id="b13e4-106">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="b13e4-106">\<backupLists></span></span>  
<span data-ttu-id="b13e4-107">\<> backupList</span><span class="sxs-lookup"><span data-stu-id="b13e4-107">\<backupList></span></span>  
<span data-ttu-id="b13e4-108">\<add></span><span class="sxs-lookup"><span data-stu-id="b13e4-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13e4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b13e4-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b13e4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b13e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b13e4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b13e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b13e4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b13e4-112">Attributes</span></span>  
  
|<span data-ttu-id="b13e4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b13e4-113">Attribute</span></span>|<span data-ttu-id="b13e4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b13e4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b13e4-115">name</span><span class="sxs-lookup"><span data-stu-id="b13e4-115">name</span></span>|<span data-ttu-id="b13e4-116">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="b13e4-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b13e4-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b13e4-117">Child Elements</span></span>  
 <span data-ttu-id="b13e4-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b13e4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b13e4-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b13e4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b13e4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b13e4-120">Element</span></span>|<span data-ttu-id="b13e4-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b13e4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b13e4-122">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="b13e4-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b13e4-123">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="b13e4-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b13e4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b13e4-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
