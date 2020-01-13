---
title: <typeparam> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 04145b82cbed0e9a5cae38ff9ef33d061ee792c9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694535"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="2573b-102">\<typeparam> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2573b-102">\<typeparam> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2573b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2573b-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2573b-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2573b-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2573b-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="2573b-105">The name of the type parameter.</span></span> <span data-ttu-id="2573b-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="2573b-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2573b-107">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="2573b-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2573b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2573b-108">Remarks</span></span>  
 <span data-ttu-id="2573b-109">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="2573b-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="2573b-110">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="2573b-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="2573b-111">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="2573b-111">For more information, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="2573b-112">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).</span><span class="sxs-lookup"><span data-stu-id="2573b-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="2573b-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2573b-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2573b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2573b-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="2573b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2573b-115">See also</span></span>

- [<span data-ttu-id="2573b-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2573b-116">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="2573b-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2573b-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2573b-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="2573b-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
