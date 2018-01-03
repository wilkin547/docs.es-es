---
title: Elemento &lt;Directives&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ca27422889fd33071a02c3a4b6fea0a6ba7eb0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="a285c-102">Elemento &lt;Directives&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="a285c-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="a285c-103">Elemento raíz de cada archivo de directivas de tiempo de ejecución para [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a285c-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a285c-104">**\<Directivas xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span><span class="sxs-lookup"><span data-stu-id="a285c-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a285c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a285c-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="a285c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a285c-106">Attributes</span></span>  
  
|<span data-ttu-id="a285c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="a285c-107">Attribute</span></span>|<span data-ttu-id="a285c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a285c-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="a285c-109">El espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="a285c-109">The XML namespace.</span></span> <span data-ttu-id="a285c-110">Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="a285c-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="a285c-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a285c-111">Child elements</span></span>  
  
|<span data-ttu-id="a285c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a285c-112">Element</span></span>|<span data-ttu-id="a285c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a285c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a285c-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="a285c-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="a285c-115">Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="a285c-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="a285c-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="a285c-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="a285c-117">Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a285c-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a285c-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a285c-118">Remarks</span></span>  
 <span data-ttu-id="a285c-119">Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="a285c-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="a285c-120">El elemento `<Directives>` puede contener cero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) y cero, uno o más elementos [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a285c-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a285c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a285c-121">See Also</span></span>  
 [<span data-ttu-id="a285c-122">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="a285c-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a285c-123">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="a285c-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
