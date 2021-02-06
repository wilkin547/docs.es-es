---
description: 'Más información sobre: <Directives> elemento (.net Native)'
title: <Directives> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 7aa3bf3718f32d55ba8189c65705868c6fb399ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662915"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="75e85-103">\<Directives> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="75e85-103">\<Directives> Element (.NET Native)</span></span>

<span data-ttu-id="75e85-104">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="75e85-104">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="75e85-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75e85-105">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="75e85-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="75e85-106">Attributes</span></span>  
  
|<span data-ttu-id="75e85-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="75e85-107">Attribute</span></span>|<span data-ttu-id="75e85-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="75e85-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="75e85-109">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="75e85-109">The XML namespace.</span></span> <span data-ttu-id="75e85-110">Su valor es siempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="75e85-110">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="75e85-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75e85-111">Child elements</span></span>  
  
|<span data-ttu-id="75e85-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="75e85-112">Element</span></span>|<span data-ttu-id="75e85-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75e85-113">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="75e85-114">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="75e85-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="75e85-115">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="75e85-115">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75e85-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75e85-116">Remarks</span></span>  

 <span data-ttu-id="75e85-117">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="75e85-117">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="75e85-118">El `<Directives>` elemento puede contener cero o un [\<Application>](application-element-net-native.md) elemento, y cero, uno o más [\<Library>](library-element-net-native.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="75e85-118">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e85-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="75e85-119">See also</span></span>

- [<span data-ttu-id="75e85-120">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="75e85-120">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="75e85-121">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="75e85-121">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
