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
ms.openlocfilehash: e67fe05507c8cb3edd7f46cad19211ba11e3b054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652401"
---
# <a name="-quiet"></a><span data-ttu-id="1bb64-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="1bb64-102">-quiet</span></span>
<span data-ttu-id="1bb64-103">Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="1bb64-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb64-104">Syntax</span></span>  
  
```  
-quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="1bb64-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1bb64-105">Remarks</span></span>  
 <span data-ttu-id="1bb64-106">De forma predeterminada, `-quiet` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="1bb64-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="1bb64-107">Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también se genera la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1bb64-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="1bb64-108">Para las aplicaciones que analizar la salida del compilador, puede ser más conveniente para el compilador que genere sólo el texto del diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="1bb64-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="1bb64-109">En el ejemplo siguiente, `Module1` genera un error que incluye código de origen cuando se compila sin `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="1bb64-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1bb64-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="1bb64-110">Output:</span></span>  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 <span data-ttu-id="1bb64-111">Compilado con `-quiet`, el compilador genera solo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1bb64-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="1bb64-112">El `-quiet` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="1bb64-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb64-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bb64-113">Example</span></span>  
 <span data-ttu-id="1bb64-114">El siguiente código compila `T2.vb` y no se mostrarán el código de diagnóstico de compilador relacionados con la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1bb64-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bb64-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb64-115">See Also</span></span>  
 [<span data-ttu-id="1bb64-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bb64-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1bb64-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bb64-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
