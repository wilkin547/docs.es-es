---
description: -pathmap (opciones del compilador de C#)
title: -pathmap (opciones del compilador de C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 707a37c6946cfcaf429552f0aeece6b87f3ad71d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125012"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="40094-103">-pathmap (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="40094-103">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="40094-104">La opción **-pathmap** del compilador especifica cómo asignar rutas físicas a los nombres de rutas de acceso de origen generados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="40094-104">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="40094-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40094-105">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="40094-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="40094-106">Arguments</span></span>

 <span data-ttu-id="40094-107">`path1` La ruta de acceso completa a los archivos de origen en el entorno actual</span><span class="sxs-lookup"><span data-stu-id="40094-107">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="40094-108">`sourcePath1` La ruta de acceso de origen sustituida por `path1` en cualquier archivo de salida</span><span class="sxs-lookup"><span data-stu-id="40094-108">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="40094-109">Para especificar varias rutas de acceso de origen asignadas, sepárelas con una coma.</span><span class="sxs-lookup"><span data-stu-id="40094-109">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="40094-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40094-110">Remarks</span></span>

<span data-ttu-id="40094-111">El compilador escribe la ruta de acceso de origen en la salida por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="40094-111">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="40094-112">La ruta de acceso de origen se sustituye por un argumento cuando se aplica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="40094-112">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="40094-113">La ruta de acceso de origen se inserta en un archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="40094-113">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="40094-114">La ruta de acceso del archivo PDB se inserta en un archivo PE (ejecutable portable).</span><span class="sxs-lookup"><span data-stu-id="40094-114">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="40094-115">Esta opción asigna cada ruta de acceso física en la máquina donde el compilador se ejecuta a una ruta de acceso correspondiente que debe escribirse en los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="40094-115">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="40094-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40094-116">Example</span></span>

<span data-ttu-id="40094-117">Compile `t.cs` en el directorio **C:\\work\\test** y asigne ese directorio a **\publish** en la salida:</span><span class="sxs-lookup"><span data-stu-id="40094-117">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="40094-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="40094-118">See also</span></span>

- [<span data-ttu-id="40094-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="40094-119">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="40094-120">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="40094-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
