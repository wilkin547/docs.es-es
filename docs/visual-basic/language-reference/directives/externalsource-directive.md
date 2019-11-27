---
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
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343828"
---
# <a name="externalsource-directive"></a><span data-ttu-id="cfaa1-102">#ExternalSource (Directiva)</span><span class="sxs-lookup"><span data-stu-id="cfaa1-102">#ExternalSource Directive</span></span>

<span data-ttu-id="cfaa1-103">Indica una asignación entre líneas específicas de código fuente y texto externo al origen.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfaa1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfaa1-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="cfaa1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="cfaa1-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="cfaa1-106">Ruta de acceso al origen externo.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="cfaa1-107">Número de línea de la primera línea del origen externo.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="cfaa1-108">La línea donde se produce el error en el origen externo.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="cfaa1-109">Finaliza el bloque `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfaa1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfaa1-110">Remarks</span></span>  

 <span data-ttu-id="cfaa1-111">Esta directiva solo la usan el compilador y el depurador.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="cfaa1-112">Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al origen, como un archivo. aspx.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="cfaa1-113">Si se encuentran errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="cfaa1-114">Las directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="cfaa1-115">Están pensadas para uso interno de la aplicación únicamente.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfaa1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfaa1-116">See also</span></span>

- [<span data-ttu-id="cfaa1-117">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="cfaa1-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
