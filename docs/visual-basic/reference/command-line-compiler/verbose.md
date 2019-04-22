---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832799"
---
# <a name="-verbose"></a><span data-ttu-id="8efd7-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="8efd7-102">-verbose</span></span>
<span data-ttu-id="8efd7-103">Hace que el compilador genere mensajes de estado y de error detallados.</span><span class="sxs-lookup"><span data-stu-id="8efd7-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8efd7-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8efd7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8efd7-105">Arguments</span></span>  
 <span data-ttu-id="8efd7-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8efd7-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="8efd7-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8efd7-107">Optional.</span></span> <span data-ttu-id="8efd7-108">Especificar `-verbose` es lo mismo que especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados.</span><span class="sxs-lookup"><span data-stu-id="8efd7-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="8efd7-109">El valor predeterminado para esta opción es `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="8efd7-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8efd7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8efd7-110">Remarks</span></span>  
 <span data-ttu-id="8efd7-111">El `-verbose` opción muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados se cargan mediante un módulo y muestra qué archivos se está compilando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8efd7-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8efd7-112">El `-verbose` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8efd7-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8efd7-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8efd7-113">Example</span></span>  
 <span data-ttu-id="8efd7-114">El siguiente código compila `In.vb` y hace que el compilador para mostrar información de estado detallada.</span><span class="sxs-lookup"><span data-stu-id="8efd7-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8efd7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8efd7-115">See also</span></span>

- [<span data-ttu-id="8efd7-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8efd7-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8efd7-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8efd7-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
