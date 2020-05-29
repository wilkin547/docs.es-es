---
title: -main (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 7d3cfce474023907eda0bc40b692e4bbb65ffb96
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802844"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="36ad8-102">-main (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="36ad8-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="36ad8-103">Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="36ad8-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ad8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36ad8-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="36ad8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="36ad8-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="36ad8-106">Tipo que contiene el método **Main**.</span><span class="sxs-lookup"><span data-stu-id="36ad8-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="36ad8-107">El nombre de clase proporcionado debe ser completo: debe incluir el espacio de nombres completo que contiene la clase, seguido del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="36ad8-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="36ad8-108">Por ejemplo, cuando el método `Main` se encuentra dentro de la clase `Program` en el espacio de nombres `MyApplication.Core`, la opción del compilador tiene que ser `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="36ad8-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="36ad8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36ad8-109">Remarks</span></span>  
 <span data-ttu-id="36ad8-110">Si la compilación incluye más de un tipo con un método [Main](../../programming-guide/main-and-command-args/index.md), puede especificar el tipo que contiene el método **Main** que quiere usar como punto de entrada en el programa.</span><span class="sxs-lookup"><span data-stu-id="36ad8-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="36ad8-111">Esta opción se usa al compilar un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="36ad8-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="36ad8-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="36ad8-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="36ad8-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="36ad8-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="36ad8-114">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="36ad8-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="36ad8-115">Modifique la propiedad **Objeto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="36ad8-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="36ad8-116">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="36ad8-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="36ad8-117">Para establecer esta opción del compilador editando manualmente el archivo. csproj</span><span class="sxs-lookup"><span data-stu-id="36ad8-117">To set this compiler option by manually editing the .csproj file</span></span>
  
<span data-ttu-id="36ad8-118">Puede establecer esta opción editando el archivo. csproj y agregando un elemento `StartupObject` dentro de la sección `PropertyGroup`.</span><span class="sxs-lookup"><span data-stu-id="36ad8-118">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="36ad8-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36ad8-119">For example:</span></span>

```
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="36ad8-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36ad8-120">Example</span></span>  
 <span data-ttu-id="36ad8-121">Compile `t2.cs` y `t3.cs` y especifique que el método **Main** se encuentra en `Test2`:</span><span class="sxs-lookup"><span data-stu-id="36ad8-121">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="36ad8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="36ad8-122">See also</span></span>

- [<span data-ttu-id="36ad8-123">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="36ad8-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="36ad8-124">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="36ad8-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
