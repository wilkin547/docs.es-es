---
title: <extensions>transversal
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918966"
---
# <a name="extensions-section"></a><span data-ttu-id="ba81d-102">\<sección de > de extensiones</span><span class="sxs-lookup"><span data-stu-id="ba81d-102">\<extensions> section</span></span>
<span data-ttu-id="ba81d-103">Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="ba81d-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="ba81d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba81d-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba81d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba81d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba81d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba81d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ba81d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba81d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba81d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba81d-108">Attributes</span></span>  
 <span data-ttu-id="ba81d-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ba81d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba81d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba81d-110">Child Elements</span></span>  
  
|<span data-ttu-id="ba81d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba81d-111">Element</span></span>|<span data-ttu-id="ba81d-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ba81d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba81d-113">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="ba81d-113">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="ba81d-114">Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ba81d-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="ba81d-115">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="ba81d-115">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="ba81d-116">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba81d-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="ba81d-117">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="ba81d-117">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="ba81d-118">Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="ba81d-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="ba81d-119">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="ba81d-119">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="ba81d-120">Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="ba81d-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba81d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba81d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ba81d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba81d-122">Element</span></span>|<span data-ttu-id="ba81d-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ba81d-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba81d-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ba81d-124">system.ServiceModel</span></span>|<span data-ttu-id="ba81d-125">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="ba81d-125">The root element of all WCF configuration elements.</span></span>|
