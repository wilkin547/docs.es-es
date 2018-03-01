---
title: -bugreport (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2a6c27454cc8f95b9662d6ae688471849c5cee0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="db23a-102">-bugreport (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="db23a-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="db23a-103">Especifica que esa información de depuración debe colocarse en un archivo para su análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="db23a-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db23a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db23a-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="db23a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="db23a-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="db23a-106">El nombre del archivo que quiere que contenga su informe de errores.</span><span class="sxs-lookup"><span data-stu-id="db23a-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db23a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db23a-107">Remarks</span></span>  
 <span data-ttu-id="db23a-108">La opción **-bugreport** especifica que la siguiente información debe colocarse en `file`:</span><span class="sxs-lookup"><span data-stu-id="db23a-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="db23a-109">Una copia de todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="db23a-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="db23a-110">Una lista de las opciones del compilador que se han usado en la compilación.</span><span class="sxs-lookup"><span data-stu-id="db23a-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="db23a-111">Información de la versión sobre su compilador, tiempo de ejecución y sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="db23a-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="db23a-112">Módulos y ensamblados a los que se hace referencia, guardados como dígitos hexadecimales, excepto los ensamblados que se proporcionan con .NET Framework y SDK.</span><span class="sxs-lookup"><span data-stu-id="db23a-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="db23a-113">Resultados del compilador, si los hay.</span><span class="sxs-lookup"><span data-stu-id="db23a-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="db23a-114">Una descripción del problema, que se le pedirá.</span><span class="sxs-lookup"><span data-stu-id="db23a-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="db23a-115">Una descripción de cómo cree que debe corregirse el problema, que se le pedirá.</span><span class="sxs-lookup"><span data-stu-id="db23a-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="db23a-116">Si esta opción se usa con **-errorreport:prompt** o **-errorreport:send**, la información del archivo se enviará a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="db23a-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="db23a-117">Como una copia de todos los archivos de código fuente se colocarán en `file`, puede que quiera reproducir el defecto en el código sospechoso en el programa más corto posible.</span><span class="sxs-lookup"><span data-stu-id="db23a-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="db23a-118">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="db23a-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="db23a-119">Tenga en cuenta que el contenido del código fuente expuesto del archivo generado puede provocar la divulgación de información involuntaria.</span><span class="sxs-lookup"><span data-stu-id="db23a-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db23a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="db23a-120">See Also</span></span>  
 [<span data-ttu-id="db23a-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="db23a-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="db23a-122">-errorreport (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="db23a-122">-errorreport (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
 [<span data-ttu-id="db23a-123">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="db23a-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
