---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: fb2b324a2c128b470f1a9a21343408280c5e1862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743249"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="efc17-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="efc17-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="efc17-103">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="efc17-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="efc17-104">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="efc17-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="efc17-105">&nbsp;&nbsp;**\<enrutamiento >** </span><span class="sxs-lookup"><span data-stu-id="efc17-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="efc17-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="efc17-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="efc17-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efc17-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efc17-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="efc17-108">Attributes and elements</span></span>

<span data-ttu-id="efc17-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="efc17-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="efc17-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="efc17-110">Attributes</span></span>

<span data-ttu-id="efc17-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="efc17-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="efc17-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="efc17-112">Child elements</span></span>

|     | <span data-ttu-id="efc17-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="efc17-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="efc17-114">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="efc17-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="efc17-115">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="efc17-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="efc17-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="efc17-116">Parent elements</span></span>

|     | <span data-ttu-id="efc17-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="efc17-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="efc17-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="efc17-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="efc17-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="efc17-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="efc17-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="efc17-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
