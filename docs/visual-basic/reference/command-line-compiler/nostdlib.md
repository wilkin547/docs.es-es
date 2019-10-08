---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005417"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="64772-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64772-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="64772-103">Hace que el compilador no haga referencia automáticamente a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="64772-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64772-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64772-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="64772-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64772-105">Remarks</span></span>  
 <span data-ttu-id="64772-106">La opción `-nostdlib` quita la referencia automática al ensamblado System. dll y evita que el compilador Lea el archivo Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="64772-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="64772-107">El archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe, hace referencia a los ensamblados .NET Framework utilizados con frecuencia e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="64772-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64772-108">Siempre se hace referencia a los ensamblados mscorlib. dll y Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="64772-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64772-109">La opción `-nostdlib` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="64772-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64772-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64772-110">Example</span></span>  
 <span data-ttu-id="64772-111">El código siguiente compila `T2.vb` sin hacer referencia a las bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="64772-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="64772-112">Debe establecer la constante de compilación condicional de `_MYTYPE` en la cadena "Empty" para quitar el objeto `My`.</span><span class="sxs-lookup"><span data-stu-id="64772-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="64772-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="64772-113">See also</span></span>

- [<span data-ttu-id="64772-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="64772-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="64772-115">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64772-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="64772-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="64772-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="64772-117">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="64772-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
