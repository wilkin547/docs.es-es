---
description: 'Más información acerca de: Directiva de #ExternalSource'
title: '#Directiva ExternalSource'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 1f2e73aa152fbe2d97edcde912626696faacd5af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797242"
---
# <a name="externalsource-directive"></a><span data-ttu-id="3e225-103">#ExternalSource (Directiva)</span><span class="sxs-lookup"><span data-stu-id="3e225-103">#ExternalSource Directive</span></span>

<span data-ttu-id="3e225-104">Indica una asignación entre líneas específicas de código fuente y texto externo al origen.</span><span class="sxs-lookup"><span data-stu-id="3e225-104">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e225-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e225-105">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="3e225-106">Partes</span><span class="sxs-lookup"><span data-stu-id="3e225-106">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="3e225-107">Ruta de acceso al origen externo.</span><span class="sxs-lookup"><span data-stu-id="3e225-107">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="3e225-108">Número de línea de la primera línea del origen externo.</span><span class="sxs-lookup"><span data-stu-id="3e225-108">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="3e225-109">La línea donde se produce el error en el origen externo.</span><span class="sxs-lookup"><span data-stu-id="3e225-109">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="3e225-110">Finaliza el bloque `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="3e225-110">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e225-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3e225-111">Remarks</span></span>  

 <span data-ttu-id="3e225-112">Esta directiva solo la usan el compilador y el depurador.</span><span class="sxs-lookup"><span data-stu-id="3e225-112">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="3e225-113">Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al origen, como un archivo. aspx.</span><span class="sxs-lookup"><span data-stu-id="3e225-113">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="3e225-114">Si se encuentran errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.</span><span class="sxs-lookup"><span data-stu-id="3e225-114">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="3e225-115">Las directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="3e225-115">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="3e225-116">Están pensadas para uso interno de la aplicación únicamente.</span><span class="sxs-lookup"><span data-stu-id="3e225-116">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e225-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e225-117">See also</span></span>

- [<span data-ttu-id="3e225-118">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="3e225-118">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
