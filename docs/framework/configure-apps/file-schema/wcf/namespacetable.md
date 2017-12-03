---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6646b94449a79c96a8720a798f48298ab32ee0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="76b81-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="76b81-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="76b81-103">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="76b81-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="76b81-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="76b81-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="76b81-105">&nbsp;&nbsp;**\<enrutamiento >** </span><span class="sxs-lookup"><span data-stu-id="76b81-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="76b81-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="76b81-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="76b81-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76b81-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="76b81-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76b81-108">Attributes and elements</span></span>

<span data-ttu-id="76b81-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76b81-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="76b81-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="76b81-110">Attributes</span></span>

<span data-ttu-id="76b81-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="76b81-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="76b81-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76b81-112">Child elements</span></span>

|     | <span data-ttu-id="76b81-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="76b81-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="76b81-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="76b81-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="76b81-115">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="76b81-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="76b81-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76b81-116">Parent elements</span></span>

|     | <span data-ttu-id="76b81-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="76b81-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="76b81-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="76b81-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="76b81-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="76b81-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="76b81-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="76b81-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
