---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202381"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="7ad11-102">\<Directives>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="7ad11-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="7ad11-103">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ad11-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="7ad11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ad11-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="7ad11-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ad11-105">Attributes</span></span>  
  
|<span data-ttu-id="7ad11-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ad11-106">Attribute</span></span>|<span data-ttu-id="7ad11-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ad11-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="7ad11-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="7ad11-108">The XML namespace.</span></span> <span data-ttu-id="7ad11-109">Su valor es siempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="7ad11-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="7ad11-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ad11-110">Child elements</span></span>  
  
|<span data-ttu-id="7ad11-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ad11-111">Element</span></span>|<span data-ttu-id="7ad11-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ad11-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="7ad11-113">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="7ad11-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="7ad11-114">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ad11-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ad11-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ad11-115">Remarks</span></span>  
 <span data-ttu-id="7ad11-116">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="7ad11-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="7ad11-117">El `<Directives>` elemento puede contener cero o un [\<Application>](application-element-net-native.md) elemento, y cero, uno o más [\<Library>](library-element-net-native.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="7ad11-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad11-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7ad11-118">See also</span></span>

- [<span data-ttu-id="7ad11-119">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="7ad11-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="7ad11-120">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7ad11-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
