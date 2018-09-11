---
title: Elemento &lt;Directives&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8921d2841f9a7b4228ae3b8735d7047453f71bcb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267146"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="d75d7-102">Elemento &lt;Directives&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="d75d7-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d75d7-103">El elemento raíz en cada archivo de directivas en tiempo de ejecución de .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d75d7-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="d75d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d75d7-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="d75d7-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d75d7-105">Attributes</span></span>  
  
|<span data-ttu-id="d75d7-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d75d7-106">Attribute</span></span>|<span data-ttu-id="d75d7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d75d7-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="d75d7-108">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="d75d7-108">The XML namespace.</span></span> <span data-ttu-id="d75d7-109">Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="d75d7-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="d75d7-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d75d7-110">Child elements</span></span>  
  
|<span data-ttu-id="d75d7-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="d75d7-111">Element</span></span>|<span data-ttu-id="d75d7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d75d7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d75d7-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="d75d7-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="d75d7-114">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="d75d7-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="d75d7-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="d75d7-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="d75d7-116">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d75d7-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d75d7-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d75d7-117">Remarks</span></span>  
 <span data-ttu-id="d75d7-118">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="d75d7-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="d75d7-119">El elemento `<Directives>` puede contener cero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) y cero, uno o más elementos [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="d75d7-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75d7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d75d7-120">See Also</span></span>  
 [<span data-ttu-id="d75d7-121">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="d75d7-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="d75d7-122">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="d75d7-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
