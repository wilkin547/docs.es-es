---
title: "Identificadores de línea, archivo y ruta de acceso de código fuente (F#)"
description: "Obtenga información acerca de cómo usar F # identificador valores integrados que permiten acceder al número de línea de origen y el directorio y el nombre de archivo en el código."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="6adbe-104">Identificadores de línea, archivo y ruta de acceso de origen</span><span class="sxs-lookup"><span data-stu-id="6adbe-104">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="6adbe-105">Los identificadores de `__LINE__`, `__SOURCE_DIRECTORY__` y `__SOURCE_FILE__` son valores integrados que permiten obtener acceso al nombre de número, el directorio y el archivo de la línea de origen en el código.</span><span class="sxs-lookup"><span data-stu-id="6adbe-105">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="6adbe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6adbe-106">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="6adbe-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6adbe-107">Remarks</span></span>
<span data-ttu-id="6adbe-108">Cada uno de estos valores tiene tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="6adbe-108">Each of these values has type `string`.</span></span>

<span data-ttu-id="6adbe-109">En la tabla siguiente se resume los identificadores de ruta de acceso que están disponibles en F #, de archivo y la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6adbe-109">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="6adbe-110">Estos identificadores no son macros de preprocesador; son valores integrados que son reconocidos por el compilador.</span><span class="sxs-lookup"><span data-stu-id="6adbe-110">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="6adbe-111">Identificador predefinido</span><span class="sxs-lookup"><span data-stu-id="6adbe-111">Predefined identifier</span></span>|<span data-ttu-id="6adbe-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6adbe-112">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="6adbe-113">Se evalúa como el número de línea actual, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="6adbe-113">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="6adbe-114">Se evalúa como la ruta de acceso completa actual del directorio de origen, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="6adbe-114">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="6adbe-115">Se evalúa como el nombre de archivo de origen actual y su ruta de acceso, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="6adbe-115">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="6adbe-116">Para obtener más información sobre la `#line` directiva, consulte [directivas de compilador](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="6adbe-116">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="6adbe-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6adbe-117">Example</span></span>

<span data-ttu-id="6adbe-118">En el ejemplo de código siguiente se muestra el uso de estos valores.</span><span class="sxs-lookup"><span data-stu-id="6adbe-118">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="6adbe-119">Resultado:</span><span class="sxs-lookup"><span data-stu-id="6adbe-119">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="6adbe-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6adbe-120">See Also</span></span>
[<span data-ttu-id="6adbe-121">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="6adbe-121">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="6adbe-122">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="6adbe-122">F# Language Reference</span></span>](index.md)
