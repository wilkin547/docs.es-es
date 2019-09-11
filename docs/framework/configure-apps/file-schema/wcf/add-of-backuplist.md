---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850544"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="f73f4-102">\<Agregar > de \<backupList ></span><span class="sxs-lookup"><span data-stu-id="f73f4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="f73f4-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="f73f4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="f73f4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f73f4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f73f4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f73f4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f73f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="f73f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="f73f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> backupLists**](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="f73f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="f73f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> backupList**](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="f73f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="f73f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="f73f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73f4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f73f4-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f73f4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f73f4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f73f4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f73f4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f73f4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f73f4-113">Attributes</span></span>  
  
|<span data-ttu-id="f73f4-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f73f4-114">Attribute</span></span>|<span data-ttu-id="f73f4-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f73f4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f73f4-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="f73f4-116">name</span></span>|<span data-ttu-id="f73f4-117">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="f73f4-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f73f4-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f73f4-118">Child Elements</span></span>  
 <span data-ttu-id="f73f4-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f73f4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f73f4-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f73f4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f73f4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f73f4-121">Element</span></span>|<span data-ttu-id="f73f4-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f73f4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f73f4-123">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="f73f4-123">\<routing></span></span>](routing.md)|<span data-ttu-id="f73f4-124">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="f73f4-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f73f4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f73f4-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
