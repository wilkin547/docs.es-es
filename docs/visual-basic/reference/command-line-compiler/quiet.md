---
title: /quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b816cadb9d805d57a14e9b5df553654dd8167af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="quiet"></a><span data-ttu-id="6339c-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="6339c-102">/quiet</span></span>
<span data-ttu-id="6339c-103">Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="6339c-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6339c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6339c-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="6339c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6339c-105">Remarks</span></span>  
 <span data-ttu-id="6339c-106">De forma predeterminada, `/quiet` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="6339c-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="6339c-107">Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también se genera la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6339c-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="6339c-108">Para las aplicaciones que analizar la salida del compilador, puede ser más conveniente para el compilador que genere sólo el texto del diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="6339c-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="6339c-109">En el ejemplo siguiente, `Module1` genera un error que incluye código de origen cuando se compila sin `/quiet`.</span><span class="sxs-lookup"><span data-stu-id="6339c-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="6339c-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="6339c-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="6339c-111">Compilado con `/quiet`, el compilador genera solo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6339c-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="6339c-112">El `/quiet` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6339c-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6339c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6339c-113">Example</span></span>  
 <span data-ttu-id="6339c-114">El siguiente código compila `T2.vb` y no se mostrarán el código de diagnóstico de compilador relacionados con la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6339c-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6339c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6339c-115">See Also</span></span>  
 [<span data-ttu-id="6339c-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6339c-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6339c-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6339c-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
