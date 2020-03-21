---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181054"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="2a6c6-102">\<Elemento directivas> (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2a6c6-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="2a6c6-103">El elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="2a6c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a6c6-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="2a6c6-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a6c6-105">Attributes</span></span>  
  
|<span data-ttu-id="2a6c6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="2a6c6-106">Attribute</span></span>|<span data-ttu-id="2a6c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a6c6-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="2a6c6-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-108">The XML namespace.</span></span> <span data-ttu-id="2a6c6-109">Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="2a6c6-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a6c6-110">Child elements</span></span>  
  
|<span data-ttu-id="2a6c6-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a6c6-111">Element</span></span>|<span data-ttu-id="2a6c6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a6c6-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a6c6-113">\<>de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2a6c6-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="2a6c6-114">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="2a6c6-115">\<Biblioteca></span><span class="sxs-lookup"><span data-stu-id="2a6c6-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="2a6c6-116">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a6c6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a6c6-117">Remarks</span></span>  
 <span data-ttu-id="2a6c6-118">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="2a6c6-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="2a6c6-119">El `<Directives>` elemento puede contener [ \<](application-element-net-native.md) cero o un elemento Application>y cero, uno o más [ \<elementos Library>.](library-element-net-native.md)</span><span class="sxs-lookup"><span data-stu-id="2a6c6-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6c6-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a6c6-120">See also</span></span>

- [<span data-ttu-id="2a6c6-121">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="2a6c6-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2a6c6-122">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2a6c6-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
