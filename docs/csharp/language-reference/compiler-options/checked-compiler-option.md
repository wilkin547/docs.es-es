---
title: -checked (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cb4dbadfa4efd0750ffd3dea88a3f661e2f85a8e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173775"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="1e927-102">-checked (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="1e927-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="1e927-103">La opción **-checked** especifica si una instrucción aritmética de enteros que produce un valor fuera del intervalo del tipo de datos y que no está en el ámbito de las palabras clave [checked](../keywords/checked.md) o [unchecked](../keywords/unchecked.md) provocará una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e927-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e927-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e927-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e927-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e927-105">Remarks</span></span>  
 <span data-ttu-id="1e927-106">Una instrucción aritmética de enteros que está en el ámbito de la palabra clave `checked` o `unchecked` no está sujeta al efecto de la opción **-checked**.</span><span class="sxs-lookup"><span data-stu-id="1e927-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="1e927-107">Si una instrucción aritmética de enteros que no está en el ámbito de la palabra clave `checked` o `unchecked` produce un valor fuera del intervalo del tipo de datos, y si se usa **-checked+** (o **-checked**) en la compilación, la instrucción provoca una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e927-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="1e927-108">Si se usa **-checked-** en la compilación, la instrucción no produce una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e927-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="1e927-109">El valor predeterminado para esta opción es **-checked-** y la comprobación de desbordamiento está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1e927-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>

 <span data-ttu-id="1e927-110">A veces, las herramientas automatizadas que se usan para compilar aplicaciones de gran tamaño establecen -check en +.</span><span class="sxs-lookup"><span data-stu-id="1e927-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="1e927-111">Una situación para usar -checked- es reemplazar el valor predeterminado global de la herramienta especificando -checked-.</span><span class="sxs-lookup"><span data-stu-id="1e927-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1e927-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1e927-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="1e927-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e927-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="1e927-114">Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="1e927-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="1e927-115">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="1e927-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="1e927-116">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="1e927-116">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="1e927-117">Modifique la propiedad **Comprobar el desbordamiento aritmético**.</span><span class="sxs-lookup"><span data-stu-id="1e927-117">Modify the **Check for arithmetic overflow** property.</span></span>  
  
 <span data-ttu-id="1e927-118">Para acceder a esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e927-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e927-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e927-119">Example</span></span>  
 <span data-ttu-id="1e927-120">El comando siguiente compila `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="1e927-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="1e927-121">El uso de `-checked` en el comando especifica que cualquier instrucción de aritmética de enteros del archivo que no esté en el ámbito de la palabra clave `checked` o `unchecked` y que produzca un valor fuera del intervalo del tipo de datos provocará una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e927-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e927-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e927-122">See also</span></span>

- [<span data-ttu-id="1e927-123">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="1e927-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1e927-124">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="1e927-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
