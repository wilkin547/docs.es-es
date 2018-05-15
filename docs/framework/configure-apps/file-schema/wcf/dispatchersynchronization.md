---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 34c12a05ee363df6b6cfc9ff3809bab50ee8d522
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="3b5e5-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="3b5e5-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="3b5e5-103">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="3b5e5-104">\<system.serviceModel > \<comportamientos > \<endpointBehaviors > \<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3b5e5-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="3b5e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b5e5-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="3b5e5-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b5e5-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="3b5e5-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b5e5-107">Attributes and elements</span></span>

<span data-ttu-id="3b5e5-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3b5e5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b5e5-109">Attributes</span></span>

| <span data-ttu-id="3b5e5-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b5e5-110">Attribute</span></span>               | <span data-ttu-id="3b5e5-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b5e5-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="3b5e5-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="3b5e5-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="3b5e5-113">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="3b5e5-114">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="3b5e5-115">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3b5e5-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b5e5-116">Child elements</span></span>

<span data-ttu-id="3b5e5-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3b5e5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b5e5-118">Parent elements</span></span>

| <span data-ttu-id="3b5e5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b5e5-119">Element</span></span> | <span data-ttu-id="3b5e5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b5e5-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="3b5e5-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3b5e5-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3b5e5-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3b5e5-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3b5e5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b5e5-123">See also</span></span>

 <span data-ttu-id="3b5e5-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="3b5e5-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
