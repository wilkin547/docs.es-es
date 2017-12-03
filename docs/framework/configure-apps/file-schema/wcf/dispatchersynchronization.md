---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0a6349f50c8810d834d7887daecb6ac9cffb2e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="9a169-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="9a169-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="9a169-103">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9a169-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="9a169-104">\<system.serviceModel > \<comportamientos > \<endpointBehaviors > \<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9a169-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="9a169-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a169-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="9a169-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="9a169-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="9a169-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a169-107">Attributes and elements</span></span>

<span data-ttu-id="9a169-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a169-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9a169-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a169-109">Attributes</span></span>

| <span data-ttu-id="9a169-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="9a169-110">Attribute</span></span>               | <span data-ttu-id="9a169-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a169-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="9a169-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="9a169-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="9a169-113">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9a169-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="9a169-114">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="9a169-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="9a169-115">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="9a169-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="9a169-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a169-116">Child elements</span></span>

<span data-ttu-id="9a169-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9a169-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9a169-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a169-118">Parent elements</span></span>

| <span data-ttu-id="9a169-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a169-119">Element</span></span> | <span data-ttu-id="9a169-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a169-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="9a169-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9a169-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9a169-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9a169-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9a169-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a169-123">See also</span></span>

 <span data-ttu-id="9a169-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="9a169-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
