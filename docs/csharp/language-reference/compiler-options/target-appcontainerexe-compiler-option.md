---
title: -target:appcontainerexe (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 64661e72f9efe190606cadd93558678cb849e8cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74204531"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="4837d-102">-target:appcontainerexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4837d-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="4837d-103">Si usa la opción del compilador **-target:appcontainerexe**, este crea un archivo ejecutable de Windows (.exe) que se debe ejecutar en un contenedor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4837d-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="4837d-104">Esta opción equivale a [-target:winexe](./target-winexe-compiler-option.md), pero está diseñada para las aplicaciones de la Tienda Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="4837d-104">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4837d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4837d-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="4837d-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4837d-106">Remarks</span></span>  
 <span data-ttu-id="4837d-107">Para exigir que la aplicación se ejecute en un contenedor de la aplicación, esta opción establece un bit en el archivo [portable ejecutable](/windows/desktop/Debug/pe-format) (PE).</span><span class="sxs-lookup"><span data-stu-id="4837d-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="4837d-108">Cuando se establece ese bit, se produce un error si el método CreateProcess intenta iniciar el archivo ejecutable fuera de un contenedor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4837d-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="4837d-109">A menos que use la opción [-out](./out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="4837d-109">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="4837d-110">Cuando se especifica esta opción en un símbolo del sistema, todos los archivos hasta la siguiente opción **-out** o **-target** se usan para crear el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4837d-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="4837d-111">Para establecer esta opción del compilador en el IDE</span><span class="sxs-lookup"><span data-stu-id="4837d-111">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="4837d-112">En el **Explorador de soluciones**, abra el menú contextual del proyecto y después elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4837d-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="4837d-113">En la pestaña **Aplicación**, en la lista **Tipo de resultado**, elija **Aplicación de la Tienda Windows**.</span><span class="sxs-lookup"><span data-stu-id="4837d-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="4837d-114">Esta opción solo está disponible para las plantillas de aplicaciones de la Tienda Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="4837d-114">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="4837d-115">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="4837d-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4837d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4837d-116">Example</span></span>  
 <span data-ttu-id="4837d-117">El comando siguiente compila `filename.cs` en un archivo ejecutable de Windows que solo se puede ejecutar en un contenedor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4837d-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="4837d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4837d-118">See also</span></span>

- [<span data-ttu-id="4837d-119">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4837d-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="4837d-120">-target:winexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4837d-120">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="4837d-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="4837d-121">C# Compiler Options</span></span>](./index.md)
