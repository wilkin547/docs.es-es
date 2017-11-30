---
title: -noconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2b15853cdd6ee9fe12b8b3ba3388a74e49c9701
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig-c-compiler-options"></a><span data-ttu-id="195ad-102">/noconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="195ad-102">/noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="195ad-103">La opción **/noconfig** comunica al compilador que no compile con el archivo csc.rsp, que está ubicado y se carga desde el mismo directorio que el archivo csc.exe.</span><span class="sxs-lookup"><span data-stu-id="195ad-103">The **/noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="195ad-104">Syntax</span></span>  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="195ad-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="195ad-105">Remarks</span></span>  
 <span data-ttu-id="195ad-106">El archivo csc.rsp hace referencia a todos los ensamblados incluidos en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="195ad-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="195ad-107">Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="195ad-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="195ad-108">Es posible modificar el archivo csc.rsp y especificar opciones de compiladores adicionales que puedan incluirse en cada compilación desde la línea de comandos con csc.exe (excepto la opción **/noconfig**).</span><span class="sxs-lookup"><span data-stu-id="195ad-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **/noconfig** option).</span></span>  
  
 <span data-ttu-id="195ad-109">El compilador procesa en último lugar las opciones que se pasan al comando **csc**.</span><span class="sxs-lookup"><span data-stu-id="195ad-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="195ad-110">Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="195ad-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="195ad-111">Si no quiere que el compilador busque y use la configuración del archivo csc.rsp, especifique **/noconfig**.</span><span class="sxs-lookup"><span data-stu-id="195ad-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **/noconfig**.</span></span>  
  
 <span data-ttu-id="195ad-112">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="195ad-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195ad-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="195ad-113">See Also</span></span>  
 [<span data-ttu-id="195ad-114">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="195ad-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="195ad-115">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="195ad-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
