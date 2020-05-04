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
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005285"
---
# <a name="-quiet"></a><span data-ttu-id="05d96-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="05d96-102">-quiet</span></span>

<span data-ttu-id="05d96-103">Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="05d96-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="05d96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05d96-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="05d96-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05d96-105">Remarks</span></span>

<span data-ttu-id="05d96-106">De forma predeterminada, `-quiet` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="05d96-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="05d96-107">Cuando el compilador informa de un error o una advertencia relacionados con la sintaxis, también genera la línea del código fuente.</span><span class="sxs-lookup"><span data-stu-id="05d96-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="05d96-108">En el caso de las aplicaciones que analizan la salida del compilador, es posible que sea más conveniente que el compilador solo genere el texto del diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="05d96-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="05d96-109">En el ejemplo siguiente, `Module1` genera un error que incluye el código fuente cuando se compila sin `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="05d96-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="05d96-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="05d96-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="05d96-111">Compilado con `-quiet`, el compilador solo genera lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05d96-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="05d96-112">La opción `-quiet` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="05d96-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="05d96-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05d96-113">Example</span></span>

<span data-ttu-id="05d96-114">En el código siguiente se compila `T2.vb` y no se muestra el código para el diagnóstico del compilador relacionado con la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="05d96-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="05d96-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="05d96-115">See also</span></span>

- [<span data-ttu-id="05d96-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05d96-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="05d96-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="05d96-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
