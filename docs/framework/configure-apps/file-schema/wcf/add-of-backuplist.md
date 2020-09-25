---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 6d8fd26170059226583a300b1b48b849666db929
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181627"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="672bc-102">\<add> de \<backupList></span><span class="sxs-lookup"><span data-stu-id="672bc-102">\<add> of \<backupList></span></span>

<span data-ttu-id="672bc-103">Representa un elemento de configuración que define un elemento de extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="672bc-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="672bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="672bc-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="672bc-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="672bc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="672bc-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="672bc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="672bc-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="672bc-107">Attributes</span></span>  
  
|<span data-ttu-id="672bc-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="672bc-108">Attribute</span></span>|<span data-ttu-id="672bc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="672bc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="672bc-110">name</span><span class="sxs-lookup"><span data-stu-id="672bc-110">name</span></span>|<span data-ttu-id="672bc-111">Cadena que especifica el nombre del extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="672bc-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="672bc-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="672bc-112">Child Elements</span></span>  

 <span data-ttu-id="672bc-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="672bc-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="672bc-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="672bc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="672bc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="672bc-115">Element</span></span>|<span data-ttu-id="672bc-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="672bc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="672bc-117">Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.</span><span class="sxs-lookup"><span data-stu-id="672bc-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="672bc-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="672bc-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
