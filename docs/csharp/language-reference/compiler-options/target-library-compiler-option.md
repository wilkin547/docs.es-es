---
title: -target:library (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: c947b2015c19d0809cab4535e989ee83ebf17fd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606396"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="18654-102">-target:library (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="18654-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="18654-103">La opción **-target:library** hace que el compilador cree una biblioteca de vínculos dinámicos (DLL) en lugar de un archivo ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="18654-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18654-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18654-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="18654-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18654-105">Remarks</span></span>  
 <span data-ttu-id="18654-106">El archivo DLL se creará con la extensión .dll.</span><span class="sxs-lookup"><span data-stu-id="18654-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="18654-107">A menos que se especifique lo contrario con la opción [-out](./out-compiler-option.md), el archivo de salida adopta el nombre del primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="18654-107">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="18654-108">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o **-target:module** para crear el archivo .dll.</span><span class="sxs-lookup"><span data-stu-id="18654-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="18654-109">Al compilar un archivo .dll, no es necesario un método [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="18654-109">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="18654-110">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18654-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="18654-111">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="18654-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="18654-112">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="18654-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="18654-113">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="18654-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="18654-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="18654-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18654-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18654-115">Example</span></span>  
 <span data-ttu-id="18654-116">Compilación de `in.cs` y creación de `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="18654-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="18654-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="18654-117">See also</span></span>

- [<span data-ttu-id="18654-118">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="18654-118">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="18654-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="18654-119">C# Compiler Options</span></span>](./index.md)
