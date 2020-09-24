---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: a7c1e06c74bd3ba62d52ef833b8ffb6a8fd594fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167176"
---
# \<serviceAuthenticationManager>

<span data-ttu-id="8e5a4-101">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e5a4-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="8e5a4-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e5a4-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e5a4-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e5a4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8e5a4-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8e5a4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e5a4-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e5a4-105">Attributes</span></span>  
  
|<span data-ttu-id="8e5a4-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e5a4-106">Attribute</span></span>|<span data-ttu-id="8e5a4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e5a4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e5a4-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="8e5a4-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="8e5a4-109">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="8e5a4-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e5a4-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e5a4-110">Child Elements</span></span>  

 <span data-ttu-id="8e5a4-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8e5a4-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e5a4-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e5a4-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8e5a4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e5a4-113">Element</span></span>|<span data-ttu-id="8e5a4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e5a4-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8e5a4-115">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8e5a4-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e5a4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e5a4-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
