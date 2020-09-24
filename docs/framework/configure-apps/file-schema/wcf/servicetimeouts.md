---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 92d3de42daf6f7baf288e3e74242381a60e76618
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153604"
---
# \<serviceTimeouts>

<span data-ttu-id="97272-101">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="97272-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="97272-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="97272-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="97272-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="97272-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97272-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97272-104">Attributes and Elements</span></span>  

 <span data-ttu-id="97272-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97272-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97272-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="97272-106">Attributes</span></span>  
  
|<span data-ttu-id="97272-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="97272-107">Attribute</span></span>|<span data-ttu-id="97272-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="97272-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="97272-109">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="97272-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="97272-110">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="97272-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97272-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97272-111">Child Elements</span></span>  

 <span data-ttu-id="97272-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97272-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97272-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97272-113">Parent Elements</span></span>  
  
|<span data-ttu-id="97272-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="97272-114">Element</span></span>|<span data-ttu-id="97272-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="97272-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="97272-116">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="97272-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97272-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="97272-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
