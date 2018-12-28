---
title: Identificadores de línea, archivo y ruta de acceso de origen
description: Obtenga información sobre cómo usar integrada F# valores de identificador que le permiten obtener acceso al origen de línea número, directorio y nombre de archivo en el código.
ms.date: 05/16/2016
ms.openlocfilehash: 4b145fe1fe20e3d7f868558e33bab26204fb0125
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656016"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="467b0-103">Identificadores de línea, archivo y ruta de acceso de origen</span><span class="sxs-lookup"><span data-stu-id="467b0-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="467b0-104">Los identificadores `__LINE__`, `__SOURCE_DIRECTORY__` y `__SOURCE_FILE__` son valores integrados que permiten tener acceso al nombre de directorio y archivo número de línea de origen en el código.</span><span class="sxs-lookup"><span data-stu-id="467b0-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="467b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="467b0-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="467b0-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="467b0-106">Remarks</span></span>

<span data-ttu-id="467b0-107">Cada uno de estos valores tiene tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="467b0-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="467b0-108">En la tabla siguiente se resume los identificadores de línea, archivo y ruta de acceso de origen que están disponibles en F#.</span><span class="sxs-lookup"><span data-stu-id="467b0-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="467b0-109">Estos identificadores no son macros de preprocesador; son valores integrados que son reconocidos por el compilador.</span><span class="sxs-lookup"><span data-stu-id="467b0-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="467b0-110">Identificador predefinido</span><span class="sxs-lookup"><span data-stu-id="467b0-110">Predefined identifier</span></span>|<span data-ttu-id="467b0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="467b0-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="467b0-112">Se evalúa como el número de línea actual, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="467b0-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="467b0-113">Se evalúa como la ruta de acceso completa actual del directorio de origen, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="467b0-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="467b0-114">Se evalúa como el nombre de archivo de origen actual y su ruta de acceso, teniendo en cuenta `#line` directivas.</span><span class="sxs-lookup"><span data-stu-id="467b0-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|

<span data-ttu-id="467b0-115">Para obtener más información sobre la `#line` la directiva, consulte [directivas de compilador](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="467b0-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="467b0-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="467b0-116">Example</span></span>

<span data-ttu-id="467b0-117">En el ejemplo de código siguiente se muestra el uso de estos valores.</span><span class="sxs-lookup"><span data-stu-id="467b0-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="467b0-118">Resultado:</span><span class="sxs-lookup"><span data-stu-id="467b0-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="467b0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="467b0-119">See also</span></span>

- [<span data-ttu-id="467b0-120">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="467b0-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="467b0-121">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="467b0-121">F# Language Reference</span></span>](index.md)
