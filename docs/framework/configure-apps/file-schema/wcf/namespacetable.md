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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 470dd2dcc2e8554bb89eec159c6b96b24795c5d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="2d814-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="2d814-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="2d814-103">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2d814-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="2d814-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="2d814-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="2d814-105">&nbsp;&nbsp;**\<enrutamiento >** </span><span class="sxs-lookup"><span data-stu-id="2d814-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="2d814-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="2d814-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2d814-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d814-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="2d814-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d814-108">Attributes and elements</span></span>

<span data-ttu-id="2d814-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d814-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2d814-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d814-110">Attributes</span></span>

<span data-ttu-id="2d814-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2d814-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="2d814-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d814-112">Child elements</span></span>

|     | <span data-ttu-id="2d814-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d814-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2d814-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="2d814-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="2d814-115">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="2d814-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="2d814-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d814-116">Parent elements</span></span>

|     | <span data-ttu-id="2d814-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d814-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2d814-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="2d814-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="2d814-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="2d814-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2d814-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d814-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
