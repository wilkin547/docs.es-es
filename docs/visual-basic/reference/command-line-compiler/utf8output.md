---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937270"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="fef74-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fef74-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="fef74-103">Muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fef74-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fef74-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fef74-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fef74-105">Arguments</span></span>  
 <span data-ttu-id="fef74-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fef74-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fef74-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fef74-107">Optional.</span></span> <span data-ttu-id="fef74-108">El valor predeterminado para esta opción `-utf8output-`es, lo que significa que la salida del compilador no utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fef74-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="fef74-109">Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="fef74-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fef74-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fef74-110">Remarks</span></span>  
 <span data-ttu-id="fef74-111">En algunas configuraciones internacionales, los resultados del compilador no se pueden mostrar correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="fef74-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="fef74-112">En tales situaciones, use `-utf8output` y redirija el resultado del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="fef74-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fef74-113">La `-utf8output` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fef74-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef74-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fef74-114">Example</span></span>  
 <span data-ttu-id="fef74-115">En el código siguiente se compila `In.vb` y se indica al compilador que muestre la salida mediante la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fef74-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fef74-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef74-116">See also</span></span>

- [<span data-ttu-id="fef74-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fef74-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fef74-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fef74-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
