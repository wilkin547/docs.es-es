---
description: -recurse (Opciones del compilador de C#)
title: -recurse (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 9e84ff95f7f0addac1c2c2d79af0ab53572da27f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193808"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="8e4f8-103">-recurse (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="8e4f8-103">-recurse (C# Compiler Options)</span></span>

<span data-ttu-id="8e4f8-104">La opción -recurse permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (dir) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-104">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e4f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e4f8-105">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e4f8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8e4f8-106">Arguments</span></span>  

 <span data-ttu-id="8e4f8-107">`dir` (opcional)</span><span class="sxs-lookup"><span data-stu-id="8e4f8-107">`dir` (optional)</span></span>  
 <span data-ttu-id="8e4f8-108">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-108">The directory in which you want the search to begin.</span></span> <span data-ttu-id="8e4f8-109">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-109">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="8e4f8-110">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-110">The file(s) to search for.</span></span> <span data-ttu-id="8e4f8-111">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e4f8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e4f8-112">Remarks</span></span>  

 <span data-ttu-id="8e4f8-113">La opción **-recurse** permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado (`dir`) o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-113">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="8e4f8-114">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar **-recurse**.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-114">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="8e4f8-115">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8e4f8-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e4f8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e4f8-116">Example</span></span>  

 <span data-ttu-id="8e4f8-117">Compila todos los archivos de C# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="8e4f8-117">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="8e4f8-118">Compila todos los archivos de C# en el directorio dir1\dir2 y los directorios que haya por debajo y genera dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="8e4f8-118">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e4f8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e4f8-119">See also</span></span>

- [<span data-ttu-id="8e4f8-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="8e4f8-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="8e4f8-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="8e4f8-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
