---
title: <exception> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <exception>. Esta etiqueta le permite especificar qué excepciones se pueden iniciar, y se puede aplicar a métodos, propiedades, eventos e indexadores.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381741"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="88b6b-104">\<exception> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88b6b-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="88b6b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88b6b-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="88b6b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88b6b-106">Parameters</span></span>

- <span data-ttu-id="88b6b-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="88b6b-107">cref = " `member`"</span></span>

  <span data-ttu-id="88b6b-108">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="88b6b-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="88b6b-109">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="88b6b-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="88b6b-110">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="88b6b-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="88b6b-111">Para más información sobre cómo dar formato a `member` para hacer referencia a un tipo genérico, consulte [Procesar el archivo XML](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="88b6b-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="88b6b-112">Descripción de la excepción.</span><span class="sxs-lookup"><span data-stu-id="88b6b-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="88b6b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88b6b-113">Remarks</span></span>

<span data-ttu-id="88b6b-114">La etiqueta `<exception>` le permite especificar qué excepciones se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="88b6b-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="88b6b-115">Esta etiqueta se puede aplicar a definiciones de métodos, propiedades, eventos e indizadores.</span><span class="sxs-lookup"><span data-stu-id="88b6b-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="88b6b-116">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="88b6b-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="88b6b-117">Para más información sobre el control de excepciones, vea [Excepciones y control de excepciones](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="88b6b-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="88b6b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88b6b-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="88b6b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="88b6b-119">See also</span></span>

- [<span data-ttu-id="88b6b-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="88b6b-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="88b6b-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="88b6b-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
