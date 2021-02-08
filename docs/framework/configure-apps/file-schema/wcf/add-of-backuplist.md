---
description: 'Más información sobre: <add> de <backupList>'
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 9855d93be011b4eaa2890c4d24392fde3b65d05a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804080"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="c25f3-103">\<add> de \<backupList></span><span class="sxs-lookup"><span data-stu-id="c25f3-103">\<add> of \<backupList></span></span>

<span data-ttu-id="c25f3-104">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="c25f3-104">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="c25f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c25f3-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c25f3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c25f3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c25f3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c25f3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c25f3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c25f3-108">Attributes</span></span>  
  
|<span data-ttu-id="c25f3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c25f3-109">Attribute</span></span>|<span data-ttu-id="c25f3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c25f3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c25f3-111">name</span><span class="sxs-lookup"><span data-stu-id="c25f3-111">name</span></span>|<span data-ttu-id="c25f3-112">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="c25f3-112">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c25f3-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c25f3-113">Child Elements</span></span>  

 <span data-ttu-id="c25f3-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c25f3-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c25f3-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c25f3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c25f3-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c25f3-116">Element</span></span>|<span data-ttu-id="c25f3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c25f3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="c25f3-118">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="c25f3-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c25f3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c25f3-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
