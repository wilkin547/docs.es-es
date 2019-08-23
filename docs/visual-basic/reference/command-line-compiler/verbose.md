---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937260"
---
# <a name="-verbose"></a><span data-ttu-id="ddd2b-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="ddd2b-102">-verbose</span></span>
<span data-ttu-id="ddd2b-103">Hace que el compilador genere mensajes de estado y de error detallados.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddd2b-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ddd2b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ddd2b-105">Arguments</span></span>  
 <span data-ttu-id="ddd2b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ddd2b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ddd2b-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-107">Optional.</span></span> <span data-ttu-id="ddd2b-108">Especificar es lo mismo que `-verbose+`especificar, que hace que el compilador emita mensajes detallados. `-verbose`</span><span class="sxs-lookup"><span data-stu-id="ddd2b-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="ddd2b-109">El valor predeterminado para esta opción `-verbose-`es.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddd2b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddd2b-110">Remarks</span></span>  
 <span data-ttu-id="ddd2b-111">La `-verbose` opción muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados está cargando un módulo y muestra los archivos que se están compilando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddd2b-112">La `-verbose` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd2b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddd2b-113">Example</span></span>  
 <span data-ttu-id="ddd2b-114">En el código siguiente se compila `In.vb` y se indica al compilador que muestre información de estado detallada.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddd2b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddd2b-115">See also</span></span>

- [<span data-ttu-id="ddd2b-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddd2b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ddd2b-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddd2b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
