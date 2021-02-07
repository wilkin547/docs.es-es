---
description: 'Más información acerca de: <extensions> sección'
title: <extensions> transversal
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 65b1de76155b1e3fbd8e5f14a5f4a1cb8c180ec1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664696"
---
# <a name="extensions-section"></a><span data-ttu-id="59dc4-103">\<extensions> transversal</span><span class="sxs-lookup"><span data-stu-id="59dc4-103">\<extensions> section</span></span>

<span data-ttu-id="59dc4-104">Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="59dc4-104">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="59dc4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59dc4-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59dc4-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59dc4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="59dc4-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59dc4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59dc4-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="59dc4-108">Attributes</span></span>  

 <span data-ttu-id="59dc4-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59dc4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59dc4-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59dc4-110">Child Elements</span></span>  
  
|<span data-ttu-id="59dc4-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="59dc4-111">Element</span></span>|<span data-ttu-id="59dc4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="59dc4-112">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="59dc4-113">Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="59dc4-113">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="59dc4-114">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59dc4-114">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="59dc4-115">Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="59dc4-115">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="59dc4-116">Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="59dc4-116">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59dc4-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59dc4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59dc4-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="59dc4-118">Element</span></span>|<span data-ttu-id="59dc4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="59dc4-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59dc4-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59dc4-120">system.ServiceModel</span></span>|<span data-ttu-id="59dc4-121">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="59dc4-121">The root element of all WCF configuration elements.</span></span>|
