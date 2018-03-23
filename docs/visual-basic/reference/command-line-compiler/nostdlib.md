---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14361c01d13238db8f820b43889716e2528097f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="cc851-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc851-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="cc851-103">Hace que el compilador no automáticamente hacen referencia a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="cc851-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc851-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc851-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc851-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc851-105">Remarks</span></span>  
 <span data-ttu-id="cc851-106">El `-nostdlib` opción quita la referencia automática al ensamblado System.dll e impide que el compilador pueda leer el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="cc851-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="cc851-107">El archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe, hace referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados e importaciones el `System` y `Microsoft.VisualBasic` los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cc851-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc851-108">Siempre hacen referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="cc851-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc851-109">El `-nostdlib` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc851-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc851-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc851-110">Example</span></span>  
 <span data-ttu-id="cc851-111">El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="cc851-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="cc851-112">Debe establecer el `_MYTYPE` constante de compilación condicional en la cadena "Vacío" Si desea quitar el `My` objeto.</span><span class="sxs-lookup"><span data-stu-id="cc851-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc851-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc851-113">See Also</span></span>  
 [<span data-ttu-id="cc851-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="cc851-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="cc851-115">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc851-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="cc851-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc851-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="cc851-117">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="cc851-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
