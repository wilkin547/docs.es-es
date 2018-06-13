---
title: -recurse (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 7d18fb2b1710e074653e054d003be762d947d1be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214594"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="0f62c-102">-recurse (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0f62c-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="0f62c-103">La opción -recurse permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (dir) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f62c-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f62c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f62c-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f62c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0f62c-105">Arguments</span></span>  
 <span data-ttu-id="0f62c-106">`dir` (opcional)</span><span class="sxs-lookup"><span data-stu-id="0f62c-106">`dir` (optional)</span></span>  
 <span data-ttu-id="0f62c-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0f62c-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="0f62c-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f62c-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="0f62c-109">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="0f62c-109">The file(s) to search for.</span></span> <span data-ttu-id="0f62c-110">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="0f62c-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f62c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f62c-111">Remarks</span></span>  
 <span data-ttu-id="0f62c-112">La opción **-recurse** permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (`dir`) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f62c-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="0f62c-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar **-recurse**.</span><span class="sxs-lookup"><span data-stu-id="0f62c-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="0f62c-114">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0f62c-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f62c-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f62c-115">Example</span></span>  
 <span data-ttu-id="0f62c-116">Compila todos los archivos de C# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="0f62c-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="0f62c-117">Compila todos los archivos de C# en el directorio dir1\dir2 y los directorios que haya por debajo y genera dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="0f62c-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f62c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f62c-118">See Also</span></span>  
 [<span data-ttu-id="0f62c-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="0f62c-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0f62c-120">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="0f62c-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
