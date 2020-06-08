---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403062"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="ad17f-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad17f-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="ad17f-103">Muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ad17f-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad17f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad17f-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad17f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad17f-105">Arguments</span></span>  
 <span data-ttu-id="ad17f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ad17f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ad17f-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ad17f-107">Optional.</span></span> <span data-ttu-id="ad17f-108">El valor predeterminado para esta opción es `-utf8output-`, lo que significa que la salida del compilador no usa la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ad17f-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="ad17f-109">Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="ad17f-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad17f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad17f-110">Remarks</span></span>  
 <span data-ttu-id="ad17f-111">En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="ad17f-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="ad17f-112">En tales situaciones, use `-utf8output` y redirija la salida del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ad17f-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad17f-113">La opción `-utf8output` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ad17f-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad17f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad17f-114">Example</span></span>  
 <span data-ttu-id="ad17f-115">En el código siguiente se compila `In.vb` y se indica al compilador que muestre el resultado con la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ad17f-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad17f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad17f-116">See also</span></span>

- [<span data-ttu-id="ad17f-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad17f-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ad17f-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad17f-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
