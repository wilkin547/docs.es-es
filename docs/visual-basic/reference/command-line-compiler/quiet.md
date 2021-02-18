---
description: Más información sobre -quiet
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 23e1b6472e80ac6ca2ecea5c4390b43722ccebb6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432733"
---
# <a name="-quiet"></a><span data-ttu-id="8268c-103">-quiet</span><span class="sxs-lookup"><span data-stu-id="8268c-103">-quiet</span></span>

<span data-ttu-id="8268c-104">Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="8268c-104">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="8268c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8268c-105">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="8268c-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8268c-106">Remarks</span></span>

<span data-ttu-id="8268c-107">De forma predeterminada, `-quiet` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="8268c-107">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="8268c-108">Cuando el compilador informa de un error o una advertencia relacionados con la sintaxis, también genera la línea del código fuente.</span><span class="sxs-lookup"><span data-stu-id="8268c-108">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="8268c-109">En el caso de las aplicaciones que analizan la salida del compilador, es posible que sea más conveniente que el compilador solo genere el texto del diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8268c-109">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="8268c-110">En el ejemplo siguiente, `Module1` genera un error que incluye el código fuente cuando se compila sin `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="8268c-110">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="8268c-111">Resultado:</span><span class="sxs-lookup"><span data-stu-id="8268c-111">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="8268c-112">Compilado con `-quiet`, el compilador solo genera lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8268c-112">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="8268c-113">La opción `-quiet` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8268c-113">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="8268c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8268c-114">Example</span></span>

<span data-ttu-id="8268c-115">En el código siguiente se compila `T2.vb` y no se muestra el código para el diagnóstico del compilador relacionado con la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8268c-115">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="8268c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8268c-116">See also</span></span>

- [<span data-ttu-id="8268c-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8268c-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8268c-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8268c-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
