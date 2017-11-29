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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 24ae6dbf0fb67b5755aca848ea7fce6abda14b0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="20c33-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="20c33-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="20c33-103">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="20c33-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="20c33-104">\<system.serviceModel > \<comportamientos > \<endpointBehaviors > \<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="20c33-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="20c33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20c33-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="20c33-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="20c33-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="20c33-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20c33-107">Attributes and elements</span></span>

<span data-ttu-id="20c33-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20c33-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="20c33-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="20c33-109">Attributes</span></span>

| <span data-ttu-id="20c33-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="20c33-110">Attribute</span></span>               | <span data-ttu-id="20c33-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="20c33-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="20c33-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="20c33-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="20c33-113">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="20c33-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="20c33-114">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="20c33-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="20c33-115">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="20c33-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="20c33-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20c33-116">Child elements</span></span>

<span data-ttu-id="20c33-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="20c33-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="20c33-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20c33-118">Parent elements</span></span>

| <span data-ttu-id="20c33-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="20c33-119">Element</span></span> | <span data-ttu-id="20c33-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="20c33-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="20c33-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="20c33-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="20c33-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="20c33-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="20c33-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="20c33-123">See also</span></span>

 <span data-ttu-id="20c33-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="20c33-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
