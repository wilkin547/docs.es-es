---
title: '&lt;filters&gt; de &lt;routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2687101aa868ae77ce0ae818afd9df906f8525c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="58149-102">&lt;filters&gt; de &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="58149-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="58149-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="58149-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="58149-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="58149-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="58149-105">&nbsp;&nbsp;[**\<enrutamiento >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="58149-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="58149-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filtros >**</span><span class="sxs-lookup"><span data-stu-id="58149-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="58149-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58149-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58149-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58149-108">Attributes and elements</span></span>

<span data-ttu-id="58149-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58149-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="58149-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="58149-110">Attributes</span></span>

<span data-ttu-id="58149-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="58149-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="58149-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58149-112">Child elements</span></span>

|     | <span data-ttu-id="58149-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="58149-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="58149-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="58149-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="58149-115">Contiene un filtro de enrutamiento que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="58149-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="58149-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58149-116">Parent elements</span></span>

|     | <span data-ttu-id="58149-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="58149-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="58149-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="58149-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="58149-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los puntos de conexión de destino para enviar mensajes cuando un coincide con el filtro.</span><span class="sxs-lookup"><span data-stu-id="58149-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="58149-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="58149-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
