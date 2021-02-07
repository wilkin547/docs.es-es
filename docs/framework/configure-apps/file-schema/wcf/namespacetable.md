---
description: 'Más información acerca de: <namespaceTable>'
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 73bfac93fba3247c02c2d86d1482af2563015a76
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684092"
---
# \<namespaceTable>

<span data-ttu-id="5f27b-102">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5f27b-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**  
  
## <a name="syntax"></a><span data-ttu-id="5f27b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f27b-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f27b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f27b-104">Attributes and elements</span></span>

<span data-ttu-id="5f27b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f27b-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f27b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f27b-106">Attributes</span></span>

<span data-ttu-id="5f27b-107">None</span><span class="sxs-lookup"><span data-stu-id="5f27b-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f27b-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f27b-108">Child elements</span></span>

|     | <span data-ttu-id="5f27b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f27b-109">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="5f27b-110">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="5f27b-110">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="5f27b-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f27b-111">Parent elements</span></span>

|     | <span data-ttu-id="5f27b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f27b-112">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="5f27b-113">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="5f27b-113">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5f27b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f27b-114">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
