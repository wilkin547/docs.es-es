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
ms.openlocfilehash: c9dd9faf63ade725bb8bea12b40390fd30c91973
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="46f63-102">&lt;filters&gt; de &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="46f63-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="46f63-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="46f63-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="46f63-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="46f63-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="46f63-105">&nbsp;&nbsp;[**\<enrutamiento >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="46f63-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="46f63-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filtros >**</span><span class="sxs-lookup"><span data-stu-id="46f63-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="46f63-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46f63-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="46f63-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46f63-108">Attributes and elements</span></span>

<span data-ttu-id="46f63-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46f63-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="46f63-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="46f63-110">Attributes</span></span>

<span data-ttu-id="46f63-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="46f63-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="46f63-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="46f63-112">Child elements</span></span>

|     | <span data-ttu-id="46f63-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="46f63-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="46f63-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="46f63-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="46f63-115">Contiene un filtro del enrutamiento que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="46f63-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="46f63-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="46f63-116">Parent elements</span></span>

|     | <span data-ttu-id="46f63-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="46f63-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="46f63-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="46f63-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="46f63-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="46f63-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="46f63-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="46f63-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
