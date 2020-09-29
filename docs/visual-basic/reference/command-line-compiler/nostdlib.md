---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4fcc5305985f5ba32b3e6ffb740c0611821215d3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097662"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="2fd87-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fd87-102">-nostdlib (Visual Basic)</span></span>

<span data-ttu-id="2fd87-103">Hace que el compilador no haga referencia automáticamente a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="2fd87-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fd87-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="2fd87-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fd87-105">Remarks</span></span>  

 <span data-ttu-id="2fd87-106">La opción `-nostdlib` quita la referencia automática al ensamblado System.dll e impide que el compilador lea el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="2fd87-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="2fd87-107">El archivo Vbc.rsp, que está en el mismo directorio que el archivo Vbc.exe, hace referencia a los ensamblados de .NET Framework que se usan habitualmente e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="2fd87-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fd87-108">Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="2fd87-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fd87-109">La opción `-nostdlib` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2fd87-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fd87-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2fd87-110">Example</span></span>  

 <span data-ttu-id="2fd87-111">El siguiente código compila `T2.vb` sin hacer referencia a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="2fd87-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="2fd87-112">La constante de compilación condicional `_MYTYPE` se debe establecer en la cadena "Empty" para quitar el objeto `My`.</span><span class="sxs-lookup"><span data-stu-id="2fd87-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fd87-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fd87-113">See also</span></span>

- [<span data-ttu-id="2fd87-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="2fd87-114">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="2fd87-115">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fd87-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2fd87-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2fd87-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="2fd87-117">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="2fd87-117">Customizing Which Objects are Available in My</span></span>](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
