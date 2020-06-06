---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398003"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="dc300-101">Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="dc300-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="dc300-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc300-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="dc300-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc300-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc300-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc300-104">Attributes and elements</span></span>  
  
<span data-ttu-id="dc300-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc300-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc300-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc300-106">Attributes</span></span>

| <span data-ttu-id="dc300-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc300-107">Attribute</span></span>               | <span data-ttu-id="dc300-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc300-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="dc300-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="dc300-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="dc300-110">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="dc300-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="dc300-111">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="dc300-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="dc300-112">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="dc300-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="dc300-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc300-113">Child elements</span></span>

<span data-ttu-id="dc300-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc300-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dc300-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc300-115">Parent elements</span></span>

| <span data-ttu-id="dc300-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc300-116">Element</span></span> | <span data-ttu-id="dc300-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc300-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="dc300-118">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dc300-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="dc300-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc300-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
