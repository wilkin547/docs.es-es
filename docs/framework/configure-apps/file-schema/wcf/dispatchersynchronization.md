---
description: 'Más información acerca de: <dispatcherSynchronization>'
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 93664dec3648ed58df7e3e5c0760f1694c60ba7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749612"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="ee9fe-102">Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="ee9fe-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee9fe-103">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="ee9fe-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee9fe-104">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee9fe-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ee9fe-105">Attributes and elements</span></span>  
  
<span data-ttu-id="ee9fe-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee9fe-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ee9fe-107">Attributes</span></span>

| <span data-ttu-id="ee9fe-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ee9fe-108">Attribute</span></span>               | <span data-ttu-id="ee9fe-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee9fe-109">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="ee9fe-110">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="ee9fe-110">asynchronousSendEnabled</span></span> | <span data-ttu-id="ee9fe-111">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-111">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="ee9fe-112">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-112">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="ee9fe-113">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-113">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="ee9fe-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ee9fe-114">Child elements</span></span>

<span data-ttu-id="ee9fe-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ee9fe-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ee9fe-116">Parent elements</span></span>

| <span data-ttu-id="ee9fe-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee9fe-117">Element</span></span> | <span data-ttu-id="ee9fe-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee9fe-118">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ee9fe-119">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ee9fe-119">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ee9fe-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee9fe-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
