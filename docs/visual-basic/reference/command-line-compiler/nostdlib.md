---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583376"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="f3b6a-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3b6a-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="f3b6a-103">Hace que el compilador no hacen referencia automáticamente a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3b6a-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="f3b6a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3b6a-105">Remarks</span></span>  
 <span data-ttu-id="f3b6a-106">El `-nostdlib` opción quita la referencia automática al ensamblado System.dll y evita que el compilador leer el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="f3b6a-107">El archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe, hace referencia a los ensamblados de .NET Framework usados e importa el `System` y `Microsoft.VisualBasic` espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3b6a-108">Los ensamblados de Mscorlib.dll y Microsoft.VisualBasic.dll siempre se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3b6a-109">El `-nostdlib` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3b6a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3b6a-110">Example</span></span>  
 <span data-ttu-id="f3b6a-111">El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="f3b6a-112">Debe establecer el `_MYTYPE` constante de compilación condicional en la cadena "Empty" para quitar el `My` objeto.</span><span class="sxs-lookup"><span data-stu-id="f3b6a-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3b6a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3b6a-113">See also</span></span>

- [<span data-ttu-id="f3b6a-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="f3b6a-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="f3b6a-115">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3b6a-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f3b6a-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3b6a-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="f3b6a-117">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="f3b6a-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
