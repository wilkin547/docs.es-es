---
title: -pdb (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: dc7ea6aae6aa429efdf1a2dca23a3d679cb21fb7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526586"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="e9443-102">-pdb (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e9443-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="e9443-103">La opción del compilador **-pdb** especifica el nombre y la ubicación del archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="e9443-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9443-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9443-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e9443-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e9443-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e9443-106">El nombre y la ubicación del archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="e9443-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9443-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9443-107">Remarks</span></span>  
 <span data-ttu-id="e9443-108">Al especificar [-debug (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), el compilador creará un archivo .pdb en el mismo directorio en que el compilador creará el archivo de salida (.exe o .dll) con un nombre de archivo que es el mismo que el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e9443-108">When you specify [-debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="e9443-109">**-pdb** le permite especificar un nombre de archivo y una ubicación distintos del valor predeterminado para el archivo .pdb.</span><span class="sxs-lookup"><span data-stu-id="e9443-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="e9443-110">No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e9443-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9443-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9443-111">Example</span></span>  
 <span data-ttu-id="e9443-112">Compile `t.cs` y cree un archivo .pdb denominado tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="e9443-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9443-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9443-113">See Also</span></span>  

- [<span data-ttu-id="e9443-114">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e9443-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="e9443-115">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e9443-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
