---
description: 'Más información acerca de: <callbackTimeouts>'
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 8e2e05ad23f661c38430ccddc615c37705e6fc44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639203"
---
# \<callbackTimeouts>

<span data-ttu-id="32a31-102">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="32a31-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="32a31-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32a31-103">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="32a31-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="32a31-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32a31-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32a31-105">Attributes and Elements</span></span>  

 <span data-ttu-id="32a31-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32a31-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32a31-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="32a31-107">Attributes</span></span>  
  
|<span data-ttu-id="32a31-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="32a31-108">Attribute</span></span>|<span data-ttu-id="32a31-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="32a31-109">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="32a31-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="32a31-110">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="32a31-111">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="32a31-111">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32a31-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32a31-112">Child Elements</span></span>  

 <span data-ttu-id="32a31-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="32a31-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32a31-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32a31-114">Parent Elements</span></span>  
  
|<span data-ttu-id="32a31-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="32a31-115">Element</span></span>|<span data-ttu-id="32a31-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="32a31-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="32a31-117">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="32a31-117">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32a31-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="32a31-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
