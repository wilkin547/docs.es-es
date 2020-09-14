---
description: -noconfig (Opciones del compilador de C#)
title: -noconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 677b96df8c6686e46c0db93eabe72dd483b947e4
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466071"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="fa28b-103">-noconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="fa28b-103">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="fa28b-104">La opción **-noconfig** comunica al compilador que no compile con el archivo csc.rsp, que está ubicado y se carga desde el mismo directorio que el archivo csc.exe.</span><span class="sxs-lookup"><span data-stu-id="fa28b-104">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa28b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa28b-105">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa28b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa28b-106">Remarks</span></span>  
 <span data-ttu-id="fa28b-107">El archivo csc.rsp hace referencia a todos los ensamblados incluidos en .NET.</span><span class="sxs-lookup"><span data-stu-id="fa28b-107">The csc.rsp file references all the assemblies shipped with .NET Framework.</span></span> <span data-ttu-id="fa28b-108">Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa28b-108">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="fa28b-109">Es posible modificar el archivo csc.rsp y especificar opciones de compiladores adicionales que puedan incluirse en cada compilación desde la línea de comandos con csc.exe (excepto la opción **-noconfig**).</span><span class="sxs-lookup"><span data-stu-id="fa28b-109">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="fa28b-110">El compilador procesa en último lugar las opciones que se pasan al comando **csc**.</span><span class="sxs-lookup"><span data-stu-id="fa28b-110">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="fa28b-111">Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="fa28b-111">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="fa28b-112">Si no quiere que el compilador busque y use la configuración del archivo csc.rsp, especifique **-noconfig**.</span><span class="sxs-lookup"><span data-stu-id="fa28b-112">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="fa28b-113">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fa28b-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa28b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa28b-114">See also</span></span>

- [<span data-ttu-id="fa28b-115">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="fa28b-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="fa28b-116">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fa28b-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
