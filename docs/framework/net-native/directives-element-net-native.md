---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049880"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="6d15c-102">\<Elemento directives > (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="6d15c-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="6d15c-103">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6d15c-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="6d15c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d15c-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="6d15c-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="6d15c-105">Attributes</span></span>  
  
|<span data-ttu-id="6d15c-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="6d15c-106">Attribute</span></span>|<span data-ttu-id="6d15c-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6d15c-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="6d15c-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="6d15c-108">The XML namespace.</span></span> <span data-ttu-id="6d15c-109">Su valor siempre es **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="6d15c-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="6d15c-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6d15c-110">Child elements</span></span>  
  
|<span data-ttu-id="6d15c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d15c-111">Element</span></span>|<span data-ttu-id="6d15c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6d15c-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d15c-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="6d15c-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="6d15c-114">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="6d15c-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="6d15c-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="6d15c-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="6d15c-116">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d15c-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d15c-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d15c-117">Remarks</span></span>  
 <span data-ttu-id="6d15c-118">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="6d15c-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="6d15c-119">El elemento `<Directives>` puede contener cero o un elemento [\<Application>](application-element-net-native.md) y cero, uno o más elementos [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="6d15c-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d15c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d15c-120">See also</span></span>

- [<span data-ttu-id="6d15c-121">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="6d15c-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="6d15c-122">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="6d15c-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
