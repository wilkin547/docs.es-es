---
title: -recurse (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="e21ac-102">/recurse (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e21ac-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="e21ac-103">La opción /recurse le permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (dir) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e21ac-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e21ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e21ac-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e21ac-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e21ac-105">Arguments</span></span>  
 <span data-ttu-id="e21ac-106">`dir` (opcional)</span><span class="sxs-lookup"><span data-stu-id="e21ac-106">`dir` (optional)</span></span>  
 <span data-ttu-id="e21ac-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e21ac-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="e21ac-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e21ac-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="e21ac-109">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="e21ac-109">The file(s) to search for.</span></span> <span data-ttu-id="e21ac-110">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="e21ac-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e21ac-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e21ac-111">Remarks</span></span>  
 <span data-ttu-id="e21ac-112">La opción **/recurse** le permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (`dir`) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e21ac-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="e21ac-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar **/recurse**.</span><span class="sxs-lookup"><span data-stu-id="e21ac-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="e21ac-114">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e21ac-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e21ac-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e21ac-115">Example</span></span>  
 <span data-ttu-id="e21ac-116">Compila todos los archivos de C# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="e21ac-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="e21ac-117">Compila todos los archivos de C# en el directorio dir1\dir2 y los directorios que haya por debajo y genera dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="e21ac-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e21ac-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e21ac-118">See Also</span></span>  
 <span data-ttu-id="e21ac-119">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="e21ac-119">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="e21ac-120">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e21ac-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

