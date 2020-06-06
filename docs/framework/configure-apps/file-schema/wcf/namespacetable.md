---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855102"
---
# \<namespaceTable>

<span data-ttu-id="bfd19-101">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="bfd19-101">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**  
  
## <a name="syntax"></a><span data-ttu-id="bfd19-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfd19-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfd19-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bfd19-103">Attributes and elements</span></span>

<span data-ttu-id="bfd19-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bfd19-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bfd19-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfd19-105">Attributes</span></span>

<span data-ttu-id="bfd19-106">None</span><span class="sxs-lookup"><span data-stu-id="bfd19-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="bfd19-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bfd19-107">Child elements</span></span>

|     | <span data-ttu-id="bfd19-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfd19-108">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="bfd19-109">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="bfd19-109">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="bfd19-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfd19-110">Parent elements</span></span>

|     | <span data-ttu-id="bfd19-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfd19-111">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="bfd19-112">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="bfd19-112">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bfd19-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bfd19-113">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
