---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 405b557568a736de3ddc3b51e265261222613131
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403036"
---
# <a name="-verbose"></a><span data-ttu-id="7f8e6-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="7f8e6-102">-verbose</span></span>
<span data-ttu-id="7f8e6-103">Hace que el compilador genere mensajes de estado y de error detallados.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f8e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f8e6-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f8e6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7f8e6-105">Arguments</span></span>  
 <span data-ttu-id="7f8e6-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7f8e6-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="7f8e6-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-107">Optional.</span></span> <span data-ttu-id="7f8e6-108">Especificar `-verbose` equivale a especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="7f8e6-109">El valor predeterminado de esta opción es `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f8e6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f8e6-110">Remarks</span></span>  
 <span data-ttu-id="7f8e6-111">La opción `-verbose` muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados carga un módulo y muestra los archivos que se están compilando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f8e6-112">La opción `-verbose` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f8e6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f8e6-113">Example</span></span>  
 <span data-ttu-id="7f8e6-114">En el código siguiente se compila `In.vb` y se indica al compilador que muestre información de estado detallada.</span><span class="sxs-lookup"><span data-stu-id="7f8e6-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f8e6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f8e6-115">See also</span></span>

- [<span data-ttu-id="7f8e6-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f8e6-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="7f8e6-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f8e6-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
