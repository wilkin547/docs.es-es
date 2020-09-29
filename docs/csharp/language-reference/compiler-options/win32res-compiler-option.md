---
description: -win32res (Opciones del compilador de C#)
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
ms.openlocfilehash: 442c788595a01db9c0a1196d9e13b2a98963a38c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204351"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="47639-103">-win32res (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="47639-103">-win32res (C# Compiler Options)</span></span>

<span data-ttu-id="47639-104">La opción **-win32res** inserta un recurso de Win32 en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="47639-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47639-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47639-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="47639-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="47639-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="47639-107">El archivo de recursos que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="47639-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47639-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47639-108">Remarks</span></span>  

 <span data-ttu-id="47639-109">Se puede crear un archivo de recursos de Win32 con el [compilador de recursos](resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="47639-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="47639-110">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="47639-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="47639-111">Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="47639-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="47639-112">Si no especifica **-win32res**, el compilador generará información de versión basada en la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47639-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="47639-113">Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47639-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="47639-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="47639-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="47639-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47639-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="47639-116">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="47639-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="47639-117">Haga clic en el botón **Archivo de recursos** y seleccione un archivo mediante el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="47639-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47639-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47639-118">Example</span></span>  

 <span data-ttu-id="47639-119">Compile `in.cs` y adjunte un archivo de recursos de Win32 `rf.res` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="47639-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="47639-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="47639-120">See also</span></span>

- [<span data-ttu-id="47639-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="47639-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="47639-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="47639-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
