---
title: '#ExternalSource (directiva)'
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
ms.openlocfilehash: 146ab41d74b45acc4063e2463baca26c7caa4652
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586596"
---
# <a name="externalsource-directive"></a><span data-ttu-id="351f7-102">#ExternalSource (Directiva)</span><span class="sxs-lookup"><span data-stu-id="351f7-102">#ExternalSource Directive</span></span>
<span data-ttu-id="351f7-103">Indica una asignación entre líneas específicas de código fuente y texto externo al código fuente.</span><span class="sxs-lookup"><span data-stu-id="351f7-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="351f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="351f7-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="351f7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="351f7-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="351f7-106">La ruta de acceso del origen externo.</span><span class="sxs-lookup"><span data-stu-id="351f7-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="351f7-107">El número de línea de la primera línea del origen externo.</span><span class="sxs-lookup"><span data-stu-id="351f7-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="351f7-108">La línea donde se produce el error en el origen externo.</span><span class="sxs-lookup"><span data-stu-id="351f7-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="351f7-109">Finaliza el bloque `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="351f7-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="351f7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="351f7-110">Remarks</span></span>  
 <span data-ttu-id="351f7-111">Esta directiva se usa únicamente por el compilador y el depurador.</span><span class="sxs-lookup"><span data-stu-id="351f7-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="351f7-112">Un archivo de código fuente puede incluir directivas de origen externo, lo que indica una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al código fuente, como un archivo .aspx.</span><span class="sxs-lookup"><span data-stu-id="351f7-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="351f7-113">Si se producen errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.</span><span class="sxs-lookup"><span data-stu-id="351f7-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="351f7-114">Directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="351f7-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="351f7-115">Están diseñados para uso interno por la aplicación únicamente.</span><span class="sxs-lookup"><span data-stu-id="351f7-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351f7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="351f7-116">See Also</span></span>  
 [<span data-ttu-id="351f7-117">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="351f7-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
