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
ms.openlocfilehash: c220c78a6d2c3109402a20f0de40fe9665d6c730
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140820"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="44bb3-103">-win32res (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="44bb3-103">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="44bb3-104">La opción **-win32res** inserta un recurso de Win32 en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="44bb3-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44bb3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44bb3-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="44bb3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="44bb3-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="44bb3-107">El archivo de recursos que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="44bb3-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44bb3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44bb3-108">Remarks</span></span>  
 <span data-ttu-id="44bb3-109">Se puede crear un archivo de recursos de Win32 con el [compilador de recursos](resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="44bb3-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="44bb3-110">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="44bb3-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="44bb3-111">Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="44bb3-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="44bb3-112">Si no especifica **-win32res**, el compilador generará información de versión basada en la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="44bb3-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="44bb3-113">Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44bb3-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="44bb3-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44bb3-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="44bb3-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="44bb3-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="44bb3-116">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="44bb3-117">Haga clic en el botón **Archivo de recursos** y seleccione un archivo mediante el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="44bb3-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44bb3-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44bb3-118">Example</span></span>  
 <span data-ttu-id="44bb3-119">Compile `in.cs` y adjunte un archivo de recursos de Win32 `rf.res` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="44bb3-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="44bb3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="44bb3-120">See also</span></span>

- [<span data-ttu-id="44bb3-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="44bb3-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="44bb3-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="44bb3-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
