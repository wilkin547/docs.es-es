---
title: '#ExternalSource (directiva) (Visual Basic)'
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
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556323"
---
# <a name="externalsource-directive"></a><span data-ttu-id="42c0b-102">#ExternalSource (Directiva)</span><span class="sxs-lookup"><span data-stu-id="42c0b-102">#ExternalSource Directive</span></span>
<span data-ttu-id="42c0b-103">Indica una asignación entre líneas específicas de código fuente y texto externo al código fuente.</span><span class="sxs-lookup"><span data-stu-id="42c0b-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42c0b-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="42c0b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="42c0b-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="42c0b-106">La ruta de acceso para el origen externo.</span><span class="sxs-lookup"><span data-stu-id="42c0b-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="42c0b-107">El número de línea de la primera línea del origen externo.</span><span class="sxs-lookup"><span data-stu-id="42c0b-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="42c0b-108">La línea donde se produce el error en el origen externo.</span><span class="sxs-lookup"><span data-stu-id="42c0b-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="42c0b-109">Finaliza el bloque `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="42c0b-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42c0b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42c0b-110">Remarks</span></span>  
 <span data-ttu-id="42c0b-111">Esta directiva se usa únicamente por el compilador y el depurador.</span><span class="sxs-lookup"><span data-stu-id="42c0b-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="42c0b-112">Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al código fuente, como un archivo .aspx.</span><span class="sxs-lookup"><span data-stu-id="42c0b-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="42c0b-113">Si se producen errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.</span><span class="sxs-lookup"><span data-stu-id="42c0b-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="42c0b-114">Directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="42c0b-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="42c0b-115">La aplicación solo están diseñados para uso interno.</span><span class="sxs-lookup"><span data-stu-id="42c0b-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c0b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="42c0b-116">See Also</span></span>  
 [<span data-ttu-id="42c0b-117">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="42c0b-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
