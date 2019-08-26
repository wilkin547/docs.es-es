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
ms.openlocfilehash: 4d967d671b3a27698b457c80ff5a8f7031dc6bcb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587411"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="2d228-102">\<value> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2d228-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2d228-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d228-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d228-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d228-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="2d228-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d228-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d228-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d228-106">Remarks</span></span>  
 <span data-ttu-id="2d228-107">La etiqueta \<value> le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d228-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="2d228-108">Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d228-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="2d228-109">Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d228-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="2d228-110">Compile con [/doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="2d228-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d228-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d228-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="2d228-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d228-112">See also</span></span>

- [<span data-ttu-id="2d228-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2d228-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2d228-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="2d228-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
