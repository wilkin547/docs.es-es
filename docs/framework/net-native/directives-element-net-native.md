---
title: Elemento &lt;Directives&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394451"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="685cd-102">Elemento &lt;Directives&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="685cd-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="685cd-103">Elemento raíz de cada archivo de directivas de tiempo de ejecución para [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="685cd-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="685cd-104">**\<Directivas xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**</span><span class="sxs-lookup"><span data-stu-id="685cd-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="685cd-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="685cd-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="685cd-106">Attributes</span></span>  
  
|<span data-ttu-id="685cd-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="685cd-107">Attribute</span></span>|<span data-ttu-id="685cd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="685cd-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="685cd-109">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="685cd-109">The XML namespace.</span></span> <span data-ttu-id="685cd-110">Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="685cd-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="685cd-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="685cd-111">Child elements</span></span>  
  
|<span data-ttu-id="685cd-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="685cd-112">Element</span></span>|<span data-ttu-id="685cd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="685cd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="685cd-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="685cd-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="685cd-115">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="685cd-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="685cd-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="685cd-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="685cd-117">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="685cd-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="685cd-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="685cd-118">Remarks</span></span>  
 <span data-ttu-id="685cd-119">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="685cd-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="685cd-120">El elemento `<Directives>` puede contener cero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) y cero, uno o más elementos [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685cd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="685cd-121">See Also</span></span>  
 [<span data-ttu-id="685cd-122">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="685cd-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="685cd-123">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="685cd-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
