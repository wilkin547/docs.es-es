---
title: <Directives> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 524c30872e218f6428491507bbfb4ca54b6061b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251105"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="bcb50-102">\<Directives> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="bcb50-102">\<Directives> Element (.NET Native)</span></span>

<span data-ttu-id="bcb50-103">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bcb50-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="bcb50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcb50-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="bcb50-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="bcb50-105">Attributes</span></span>  
  
|<span data-ttu-id="bcb50-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="bcb50-106">Attribute</span></span>|<span data-ttu-id="bcb50-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcb50-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="bcb50-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bcb50-108">The XML namespace.</span></span> <span data-ttu-id="bcb50-109">Su valor es siempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="bcb50-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="bcb50-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bcb50-110">Child elements</span></span>  
  
|<span data-ttu-id="bcb50-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="bcb50-111">Element</span></span>|<span data-ttu-id="bcb50-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcb50-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="bcb50-113">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="bcb50-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="bcb50-114">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcb50-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcb50-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bcb50-115">Remarks</span></span>  

 <span data-ttu-id="bcb50-116">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="bcb50-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="bcb50-117">El `<Directives>` elemento puede contener cero o un [\<Application>](application-element-net-native.md) elemento, y cero, uno o más [\<Library>](library-element-net-native.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="bcb50-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb50-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcb50-118">See also</span></span>

- [<span data-ttu-id="bcb50-119">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="bcb50-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="bcb50-120">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bcb50-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
