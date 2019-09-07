---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398003"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="76a39-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="76a39-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="76a39-102">Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="76a39-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="76a39-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76a39-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76a39-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="76a39-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="76a39-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="76a39-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="76a39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="76a39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="76a39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="76a39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="76a39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dispatcherSynchronization**</span><span class="sxs-lookup"><span data-stu-id="76a39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a39-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76a39-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="76a39-110">Type</span><span class="sxs-lookup"><span data-stu-id="76a39-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76a39-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76a39-111">Attributes and elements</span></span>  
  
<span data-ttu-id="76a39-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76a39-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76a39-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="76a39-113">Attributes</span></span>

| <span data-ttu-id="76a39-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="76a39-114">Attribute</span></span>               | <span data-ttu-id="76a39-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="76a39-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="76a39-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="76a39-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="76a39-117">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="76a39-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="76a39-118">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="76a39-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="76a39-119">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="76a39-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="76a39-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76a39-120">Child elements</span></span>

<span data-ttu-id="76a39-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76a39-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="76a39-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76a39-122">Parent elements</span></span>

| <span data-ttu-id="76a39-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="76a39-123">Element</span></span> | <span data-ttu-id="76a39-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="76a39-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="76a39-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="76a39-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="76a39-126">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76a39-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="76a39-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="76a39-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
