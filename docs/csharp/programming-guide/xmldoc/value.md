---
title: '&lt;value&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 24ef4aba13668cd04e20f17ebffac9eb68e796ca
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081861"
---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="d9a6c-102">&lt;value&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d9a6c-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d9a6c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a6c-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9a6c-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9a6c-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="d9a6c-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9a6c-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9a6c-106">Remarks</span></span>  
 <span data-ttu-id="d9a6c-107">La etiqueta \<value> le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="d9a6c-108">Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="d9a6c-109">Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="d9a6c-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9a6c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9a6c-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d9a6c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a6c-112">See Also</span></span>

- [<span data-ttu-id="d9a6c-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d9a6c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d9a6c-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="d9a6c-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
