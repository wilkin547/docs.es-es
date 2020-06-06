---
title: <extensions>transversal
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855358"
---
# <a name="extensions-section"></a><span data-ttu-id="fe4fc-102">\<extensions>transversal</span><span class="sxs-lookup"><span data-stu-id="fe4fc-102">\<extensions> section</span></span>
<span data-ttu-id="fe4fc-103">Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="fe4fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe4fc-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe4fc-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fe4fc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fe4fc-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe4fc-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="fe4fc-107">Attributes</span></span>  
 <span data-ttu-id="fe4fc-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe4fc-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fe4fc-109">Child Elements</span></span>  
  
|<span data-ttu-id="fe4fc-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe4fc-110">Element</span></span>|<span data-ttu-id="fe4fc-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe4fc-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="fe4fc-112">Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="fe4fc-113">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="fe4fc-114">Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="fe4fc-115">Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe4fc-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fe4fc-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fe4fc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe4fc-117">Element</span></span>|<span data-ttu-id="fe4fc-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe4fc-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe4fc-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe4fc-119">system.ServiceModel</span></span>|<span data-ttu-id="fe4fc-120">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="fe4fc-120">The root element of all WCF configuration elements.</span></span>|
