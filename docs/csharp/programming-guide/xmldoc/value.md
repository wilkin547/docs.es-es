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
ms.openlocfilehash: 3495a6c88d340342362d84d6ea3f12048d42b21f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982159"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="d5946-102">\<value> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d5946-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d5946-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5946-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5946-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5946-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="d5946-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5946-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5946-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5946-106">Remarks</span></span>  
 <span data-ttu-id="d5946-107">La etiqueta \<value> le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5946-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="d5946-108">Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5946-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="d5946-109">Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5946-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="d5946-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d5946-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5946-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5946-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="d5946-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5946-112">See also</span></span>

- [<span data-ttu-id="d5946-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d5946-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d5946-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="d5946-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
