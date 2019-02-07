---
title: <value> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 1a1a4beb4a3412fe7739a69ecd0fed650b332fb2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263948"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="03441-102">\<value> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="03441-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="03441-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03441-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03441-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03441-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="03441-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="03441-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03441-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03441-106">Remarks</span></span>  
 <span data-ttu-id="03441-107">La etiqueta \<value> le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="03441-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="03441-108">Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="03441-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="03441-109">Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="03441-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="03441-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="03441-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03441-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03441-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="03441-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="03441-112">See also</span></span>

- [<span data-ttu-id="03441-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="03441-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="03441-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="03441-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
