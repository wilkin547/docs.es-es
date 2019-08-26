---
title: <typeparam> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: ea48cf0cdfc2dc48ad29ab6219449f801739bc8f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587598"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="d9d27-102">\<typeparam> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d9d27-102">\<typeparam> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d9d27-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9d27-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9d27-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9d27-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d9d27-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="d9d27-105">The name of the type parameter.</span></span> <span data-ttu-id="d9d27-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="d9d27-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d9d27-107">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="d9d27-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d27-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9d27-108">Remarks</span></span>  
 <span data-ttu-id="d9d27-109">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="d9d27-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="d9d27-110">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="d9d27-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="d9d27-111">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="d9d27-111">For more information, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="d9d27-112">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).</span><span class="sxs-lookup"><span data-stu-id="d9d27-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="d9d27-113">Compile con [/doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d9d27-113">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9d27-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9d27-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="d9d27-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d27-115">See also</span></span>

- [<span data-ttu-id="d9d27-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d9d27-116">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="d9d27-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d9d27-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d9d27-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="d9d27-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
