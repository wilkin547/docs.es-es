---
title: <extensions>transversal
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855358"
---
# <a name="extensions-section"></a><span data-ttu-id="3608d-102">\<sección de > de extensiones</span><span class="sxs-lookup"><span data-stu-id="3608d-102">\<extensions> section</span></span>
<span data-ttu-id="3608d-103">Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="3608d-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="3608d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3608d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3608d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3608d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3608d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> de extensiones**</span><span class="sxs-lookup"><span data-stu-id="3608d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3608d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3608d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3608d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3608d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3608d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3608d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3608d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3608d-110">Attributes</span></span>  
 <span data-ttu-id="3608d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3608d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3608d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3608d-112">Child Elements</span></span>  
  
|<span data-ttu-id="3608d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3608d-113">Element</span></span>|<span data-ttu-id="3608d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3608d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3608d-115">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="3608d-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="3608d-116">Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3608d-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="3608d-117">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="3608d-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="3608d-118">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3608d-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="3608d-119">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="3608d-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="3608d-120">Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="3608d-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="3608d-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="3608d-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="3608d-122">Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="3608d-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3608d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3608d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3608d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3608d-124">Element</span></span>|<span data-ttu-id="3608d-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3608d-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3608d-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3608d-126">system.ServiceModel</span></span>|<span data-ttu-id="3608d-127">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="3608d-127">The root element of all WCF configuration elements.</span></span>|
