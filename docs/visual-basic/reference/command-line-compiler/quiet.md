---
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
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788852"
---
# <a name="-quiet"></a><span data-ttu-id="7563b-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="7563b-102">-quiet</span></span>

<span data-ttu-id="7563b-103">Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7563b-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="7563b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7563b-104">Syntax</span></span>

```
-quiet
```

## <a name="remarks"></a><span data-ttu-id="7563b-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7563b-105">Remarks</span></span>

<span data-ttu-id="7563b-106">De forma predeterminada, `-quiet` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="7563b-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="7563b-107">Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también genera la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="7563b-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="7563b-108">Para las aplicaciones que analizar la salida del compilador, puede ser más conveniente para el compilador genere sólo el texto del diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="7563b-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="7563b-109">En el ejemplo siguiente, `Module1` produce un error que incluye código de origen cuando se compila sin `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="7563b-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="7563b-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="7563b-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="7563b-111">Compilado con `-quiet`, el compilador sólo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7563b-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="7563b-112">El `-quiet` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7563b-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="7563b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7563b-113">Example</span></span>

<span data-ttu-id="7563b-114">El siguiente código compila `T2.vb` y no se muestra código de los diagnósticos de compilador relacionados con la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="7563b-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="7563b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7563b-115">See also</span></span>

- [<span data-ttu-id="7563b-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7563b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7563b-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7563b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
