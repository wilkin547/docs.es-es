---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 55b5565ffe9d3e9e7ea41d2a2e2f380490be1781
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151428"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="b2c79-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="b2c79-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="b2c79-103">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b2c79-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="b2c79-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="b2c79-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="b2c79-105">&nbsp;&nbsp;**\<enrutamiento >** </span><span class="sxs-lookup"><span data-stu-id="b2c79-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="b2c79-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="b2c79-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b2c79-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2c79-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2c79-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b2c79-108">Attributes and elements</span></span>

<span data-ttu-id="b2c79-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b2c79-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2c79-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2c79-110">Attributes</span></span>

<span data-ttu-id="b2c79-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b2c79-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="b2c79-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b2c79-112">Child elements</span></span>

|     | <span data-ttu-id="b2c79-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2c79-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b2c79-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="b2c79-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="b2c79-115">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="b2c79-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b2c79-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b2c79-116">Parent elements</span></span>

|     | <span data-ttu-id="b2c79-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2c79-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b2c79-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="b2c79-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="b2c79-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="b2c79-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b2c79-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c79-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
