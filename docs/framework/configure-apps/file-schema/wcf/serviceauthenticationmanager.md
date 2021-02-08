---
description: 'Más información acerca de: <serviceAuthenticationManager>'
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: ae9c8d7f74b3ad7d0c61a77d20f38f228c695970
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786777"
---
# \<serviceAuthenticationManager>

<span data-ttu-id="b2d2a-102">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="b2d2a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2d2a-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2d2a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b2d2a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b2d2a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2d2a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2d2a-106">Attributes</span></span>  
  
|<span data-ttu-id="b2d2a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="b2d2a-107">Attribute</span></span>|<span data-ttu-id="b2d2a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d2a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2d2a-109">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="b2d2a-109">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="b2d2a-110">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-110">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2d2a-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b2d2a-111">Child Elements</span></span>  

 <span data-ttu-id="b2d2a-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2d2a-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b2d2a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="b2d2a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2d2a-114">Element</span></span>|<span data-ttu-id="b2d2a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d2a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b2d2a-116">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2d2a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2d2a-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
