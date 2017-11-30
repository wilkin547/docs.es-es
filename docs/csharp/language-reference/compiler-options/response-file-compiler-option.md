---
title: '@ (Opciones del compilador de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4dc8c81a9afd60add4c2a62be6804a0f6446124
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="-c-compiler-options"></a><span data-ttu-id="cb1c0-102">@ (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="cb1c0-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="cb1c0-103">La opción @ le permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb1c0-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb1c0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cb1c0-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="cb1c0-106">Un archivo que enumera las opciones del compilador o los archivos de código fuente que se compilarán.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb1c0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb1c0-107">Remarks</span></span>  
 <span data-ttu-id="cb1c0-108">El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubieran especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="cb1c0-109">Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="cb1c0-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb1c0-110">For example:</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="cb1c0-111">En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="cb1c0-112">Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias líneas).</span><span class="sxs-lookup"><span data-stu-id="cb1c0-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="cb1c0-113">Los archivos de respuesta pueden tener comentarios que comiencen con el símbolo #.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="cb1c0-114">Especificar opciones del compilador desde un archivo de respuesta es igual que enviar esos comandos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="cb1c0-115">Vea [Compilar desde la línea de comandos](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-115">See [Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="cb1c0-116">El compilador procesa las opciones de comando a medida que se encuentran.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="cb1c0-117">Por tanto, los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="cb1c0-118">Por el contrario, las opciones en un archivo de respuesta reemplazarán las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="cb1c0-119">C# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="cb1c0-120">Vea [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) para obtener más información sobre csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-120">See [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="cb1c0-121">No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="cb1c0-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb1c0-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb1c0-122">Example</span></span>  
 <span data-ttu-id="cb1c0-123">Estas son algunas líneas de un archivo de respuesta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb1c0-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb1c0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb1c0-124">See Also</span></span>  
 [<span data-ttu-id="cb1c0-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="cb1c0-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
