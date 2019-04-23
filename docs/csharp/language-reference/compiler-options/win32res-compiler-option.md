---
title: -win32res (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 4026fcbd7dc2ef29c1e7ee01a0f37b3ff471b187
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322387"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="2be3e-102">-win32res (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="2be3e-102">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="2be3e-103">La opción **-win32res** inserta un recurso de Win32 en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="2be3e-103">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2be3e-104">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="2be3e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2be3e-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="2be3e-106">El archivo de recursos que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="2be3e-106">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2be3e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2be3e-107">Remarks</span></span>  
 <span data-ttu-id="2be3e-108">Se puede crear un archivo de recursos de Win32 con el [compilador de recursos](../../language-reference/compiler-options/resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2be3e-108">A Win32 resource file can be created with the [Resource Compiler](../../language-reference/compiler-options/resource-compiler-option.md).</span></span> <span data-ttu-id="2be3e-109">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="2be3e-109">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="2be3e-110">Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="2be3e-110">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="2be3e-111">Si no especifica **-win32res**, el compilador generará información de versión basada en la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2be3e-111">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="2be3e-112">Vea [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (para hacer referencia) o [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2be3e-112">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2be3e-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2be3e-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="2be3e-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2be3e-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="2be3e-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="2be3e-116">Haga clic en el botón **Archivo de recursos** y seleccione un archivo mediante el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="2be3e-116">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2be3e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2be3e-117">Example</span></span>  
 <span data-ttu-id="2be3e-118">Compile `in.cs` y adjunte un archivo de recursos de Win32 `rf.res` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="2be3e-118">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="2be3e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2be3e-119">See also</span></span>

- [<span data-ttu-id="2be3e-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="2be3e-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="2be3e-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="2be3e-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
