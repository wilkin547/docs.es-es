---
description: 'Más información acerca de: <serviceTimeouts>'
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: bc9ef99078f8c6fa3b441604e14df928eec054e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682733"
---
# \<serviceTimeouts>

<span data-ttu-id="1bb95-102">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb95-102">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="1bb95-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb95-103">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="1bb95-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="1bb95-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bb95-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1bb95-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1bb95-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1bb95-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bb95-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1bb95-107">Attributes</span></span>  
  
|<span data-ttu-id="1bb95-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1bb95-108">Attribute</span></span>|<span data-ttu-id="1bb95-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bb95-109">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="1bb95-110">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="1bb95-110">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="1bb95-111">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="1bb95-111">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bb95-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1bb95-112">Child Elements</span></span>  

 <span data-ttu-id="1bb95-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1bb95-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bb95-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1bb95-114">Parent Elements</span></span>  
  
|<span data-ttu-id="1bb95-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bb95-115">Element</span></span>|<span data-ttu-id="1bb95-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bb95-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1bb95-117">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1bb95-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bb95-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb95-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
