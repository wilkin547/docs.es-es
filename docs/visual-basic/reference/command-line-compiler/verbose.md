---
description: Más información sobre -verbose
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: ea222d4f284bcaf163b142269fe250a081b0ee4f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470141"
---
# <a name="-verbose"></a><span data-ttu-id="b7b73-103">-verbose</span><span class="sxs-lookup"><span data-stu-id="b7b73-103">-verbose</span></span>

<span data-ttu-id="b7b73-104">Hace que el compilador genere mensajes de estado y de error detallados.</span><span class="sxs-lookup"><span data-stu-id="b7b73-104">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7b73-105">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b7b73-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b7b73-106">Arguments</span></span>  

 <span data-ttu-id="b7b73-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b7b73-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="b7b73-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7b73-108">Optional.</span></span> <span data-ttu-id="b7b73-109">Especificar `-verbose` equivale a especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados.</span><span class="sxs-lookup"><span data-stu-id="b7b73-109">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="b7b73-110">El valor predeterminado de esta opción es `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="b7b73-110">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b73-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7b73-111">Remarks</span></span>  

 <span data-ttu-id="b7b73-112">La opción `-verbose` muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados carga un módulo y muestra los archivos que se están compilando actualmente.</span><span class="sxs-lookup"><span data-stu-id="b7b73-112">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7b73-113">La opción `-verbose` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b7b73-113">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7b73-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7b73-114">Example</span></span>  

 <span data-ttu-id="b7b73-115">En el código siguiente se compila `In.vb` y se indica al compilador que muestre información de estado detallada.</span><span class="sxs-lookup"><span data-stu-id="b7b73-115">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7b73-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7b73-116">See also</span></span>

- [<span data-ttu-id="b7b73-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7b73-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b7b73-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7b73-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
