---
title: '#<a name="externalsource-directive"></a>ExternalSource (directiva)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a><span data-ttu-id="0947d-102">#ExternalSource (Directiva)</span><span class="sxs-lookup"><span data-stu-id="0947d-102">#ExternalSource Directive</span></span>
<span data-ttu-id="0947d-103">Indica una asignación entre líneas específicas de código fuente y texto externo al código fuente.</span><span class="sxs-lookup"><span data-stu-id="0947d-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0947d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0947d-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="0947d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="0947d-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="0947d-106">La ruta de acceso del origen externo.</span><span class="sxs-lookup"><span data-stu-id="0947d-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="0947d-107">El número de línea de la primera línea del origen externo.</span><span class="sxs-lookup"><span data-stu-id="0947d-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="0947d-108">La línea donde se produce el error en el origen externo.</span><span class="sxs-lookup"><span data-stu-id="0947d-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="0947d-109">Finaliza el bloque `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="0947d-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0947d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0947d-110">Remarks</span></span>  
 <span data-ttu-id="0947d-111">Esta directiva se usa únicamente por el compilador y el depurador.</span><span class="sxs-lookup"><span data-stu-id="0947d-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="0947d-112">Un archivo de código fuente puede incluir directivas de origen externo, lo que indica una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al código fuente, como un archivo .aspx.</span><span class="sxs-lookup"><span data-stu-id="0947d-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="0947d-113">Si se producen errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.</span><span class="sxs-lookup"><span data-stu-id="0947d-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="0947d-114">Directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="0947d-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="0947d-115">Están diseñados para uso interno por la aplicación únicamente.</span><span class="sxs-lookup"><span data-stu-id="0947d-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0947d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0947d-116">See Also</span></span>  
 [<span data-ttu-id="0947d-117">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="0947d-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
