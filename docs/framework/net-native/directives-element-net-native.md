---
title: <Directives> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100228"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="96784-102">\<Directivas > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="96784-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="96784-103">El elemento raíz en cada archivo de directivas en tiempo de ejecución de .NET Native.</span><span class="sxs-lookup"><span data-stu-id="96784-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="96784-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96784-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="96784-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="96784-105">Attributes</span></span>  
  
|<span data-ttu-id="96784-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="96784-106">Attribute</span></span>|<span data-ttu-id="96784-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="96784-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="96784-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="96784-108">The XML namespace.</span></span> <span data-ttu-id="96784-109">Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="96784-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="96784-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="96784-110">Child elements</span></span>  
  
|<span data-ttu-id="96784-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="96784-111">Element</span></span>|<span data-ttu-id="96784-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96784-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96784-113">\<Aplicación ></span><span class="sxs-lookup"><span data-stu-id="96784-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="96784-114">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="96784-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="96784-115">\<Biblioteca ></span><span class="sxs-lookup"><span data-stu-id="96784-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="96784-116">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96784-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96784-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96784-117">Remarks</span></span>  
 <span data-ttu-id="96784-118">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="96784-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="96784-119">El elemento `<Directives>` puede contener cero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) y cero, uno o más elementos [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="96784-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96784-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="96784-120">See also</span></span>

- [<span data-ttu-id="96784-121">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="96784-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="96784-122">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="96784-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
