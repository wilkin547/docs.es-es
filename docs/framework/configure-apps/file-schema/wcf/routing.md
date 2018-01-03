---
title: '&lt;enrutamiento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ef71753a4b0ff20a966842119adb6e637ded1f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltroutinggt"></a><span data-ttu-id="4f6eb-102">&lt;enrutamiento&gt;</span><span class="sxs-lookup"><span data-stu-id="4f6eb-102">&lt;routing&gt;</span></span>

<span data-ttu-id="4f6eb-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="4f6eb-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="4f6eb-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="4f6eb-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="4f6eb-105">&nbsp;&nbsp;**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="4f6eb-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4f6eb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f6eb-106">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f6eb-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f6eb-107">Attributes and elements</span></span>

<span data-ttu-id="4f6eb-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f6eb-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f6eb-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f6eb-109">Attributes</span></span>

<span data-ttu-id="4f6eb-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4f6eb-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f6eb-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f6eb-111">Child elements</span></span>

|     | <span data-ttu-id="4f6eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f6eb-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4f6eb-113">**\<filtros >**</span><span class="sxs-lookup"><span data-stu-id="4f6eb-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="4f6eb-114">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de MessageFilter de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="4f6eb-114">Contains a set of routing filters that determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="4f6eb-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="4f6eb-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="4f6eb-116">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="4f6eb-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="4f6eb-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f6eb-117">Parent elements</span></span>

|     | <span data-ttu-id="4f6eb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f6eb-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="4f6eb-119">**\<sistema. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="4f6eb-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="4f6eb-120">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="4f6eb-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4f6eb-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f6eb-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
