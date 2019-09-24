---
title: Identificadores de línea, archivo y ruta de acceso de origen
description: Aprenda a usar valores de F# identificador integrados que le permiten tener acceso al número de línea de código fuente, el directorio y el nombre de archivo en el código.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216746"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="6f9a4-103">Identificadores de línea, archivo y ruta de acceso de origen</span><span class="sxs-lookup"><span data-stu-id="6f9a4-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="6f9a4-104">Los identificadores `__LINE__` `__SOURCE_DIRECTORY__` y`__SOURCE_FILE__` son valores integrados que le permiten tener acceso al número de línea de código fuente, el directorio y el nombre de archivo en el código.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f9a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f9a4-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="6f9a4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f9a4-106">Remarks</span></span>

<span data-ttu-id="6f9a4-107">Cada uno de estos valores tiene `string`el tipo.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="6f9a4-108">En la tabla siguiente se resumen los identificadores de línea, archivo y ruta de acceso de origen F#que están disponibles en.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="6f9a4-109">Estos identificadores no son macros de preprocesador; son valores integrados que reconoce el compilador.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="6f9a4-110">Identificador predefinido</span><span class="sxs-lookup"><span data-stu-id="6f9a4-110">Predefined identifier</span></span>|<span data-ttu-id="6f9a4-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f9a4-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="6f9a4-112">Se evalúa como el número de línea actual, `#line` teniendo en cuenta las directivas.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="6f9a4-113">Se evalúa como la ruta de acceso completa actual del directorio de origen `#line` , teniendo en cuenta las directivas.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="6f9a4-114">Se evalúa como el nombre del archivo de código fuente actual, sin su `#line` ruta de acceso, teniendo en cuenta las directivas.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="6f9a4-115">Para obtener más información sobre `#line` la Directiva, vea [directivas de compilador](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="6f9a4-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="6f9a4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f9a4-116">Example</span></span>

<span data-ttu-id="6f9a4-117">En el ejemplo de código siguiente se muestra el uso de estos valores.</span><span class="sxs-lookup"><span data-stu-id="6f9a4-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="6f9a4-118">Resultado:</span><span class="sxs-lookup"><span data-stu-id="6f9a4-118">Output:</span></span>

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="6f9a4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f9a4-119">See also</span></span>

- [<span data-ttu-id="6f9a4-120">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="6f9a4-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="6f9a4-121">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="6f9a4-121">F# Language Reference</span></span>](index.md)
