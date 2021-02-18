---
description: Más información sobre -utf8output (Visual Basic)
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 317c1be3f18150ae88bb8e95927d9f5faf0e4f3c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461897"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="45b68-103">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45b68-103">-utf8output (Visual Basic)</span></span>

<span data-ttu-id="45b68-104">Muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="45b68-104">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45b68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45b68-105">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="45b68-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45b68-106">Arguments</span></span>  

 <span data-ttu-id="45b68-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="45b68-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="45b68-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="45b68-108">Optional.</span></span> <span data-ttu-id="45b68-109">El valor predeterminado para esta opción es `-utf8output-`, lo que significa que la salida del compilador no usa la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="45b68-109">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="45b68-110">Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="45b68-110">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45b68-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45b68-111">Remarks</span></span>  

 <span data-ttu-id="45b68-112">En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="45b68-112">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="45b68-113">En tales situaciones, use `-utf8output` y redirija la salida del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="45b68-113">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45b68-114">La opción `-utf8output` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="45b68-114">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45b68-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45b68-115">Example</span></span>  

 <span data-ttu-id="45b68-116">En el código siguiente se compila `In.vb` y se indica al compilador que muestre el resultado con la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="45b68-116">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="45b68-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="45b68-117">See also</span></span>

- [<span data-ttu-id="45b68-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45b68-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="45b68-119">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="45b68-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
