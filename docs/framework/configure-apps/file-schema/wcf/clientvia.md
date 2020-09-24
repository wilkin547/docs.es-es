---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151108"
---
# \<clientVia>

<span data-ttu-id="6aa8f-101">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="6aa8f-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="6aa8f-102">Para obtener más información, vea <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="6aa8f-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="6aa8f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6aa8f-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aa8f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6aa8f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6aa8f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6aa8f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6aa8f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="6aa8f-106">Attributes</span></span>  
  
|<span data-ttu-id="6aa8f-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="6aa8f-107">Attribute</span></span>|<span data-ttu-id="6aa8f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aa8f-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="6aa8f-109">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="6aa8f-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6aa8f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6aa8f-110">Child Elements</span></span>  

 <span data-ttu-id="6aa8f-111">None</span><span class="sxs-lookup"><span data-stu-id="6aa8f-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6aa8f-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6aa8f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="6aa8f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6aa8f-113">Element</span></span>|<span data-ttu-id="6aa8f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aa8f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6aa8f-115">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6aa8f-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6aa8f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa8f-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
