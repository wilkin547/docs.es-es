---
title: '@ (Especificar archivo de respuesta, Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: deab111cc669941a1cd7dc143dd699b6521221bb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004992"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="318b6-102">@ (Especificar archivo de respuesta, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="318b6-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="318b6-103">Especifica un archivo que contiene las opciones del compilador y los archivos de código fuente que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="318b6-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="318b6-104">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="318b6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="318b6-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="318b6-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="318b6-106">Required.</span></span> <span data-ttu-id="318b6-107">Archivo que muestra las opciones del compilador o los archivos de código fuente que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="318b6-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="318b6-108">Escriba el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="318b6-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="318b6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="318b6-109">Remarks</span></span>  
 <span data-ttu-id="318b6-110">El compilador procesa las opciones del compilador y los archivos de código fuente especificados en un archivo de respuesta como si hubieran sido especificados en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="318b6-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="318b6-111">Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como las siguientes.</span><span class="sxs-lookup"><span data-stu-id="318b6-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="318b6-112">En un archivo de respuesta, pueden aparecer varias opciones del compilador y archivos de código fuente en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="318b6-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="318b6-113">Una única especificación de opción de compilador debe aparecer en una línea (no puede abarcar varias líneas).</span><span class="sxs-lookup"><span data-stu-id="318b6-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="318b6-114">Los archivos de respuesta pueden tener comentarios que comienzan con el símbolo `#`.</span><span class="sxs-lookup"><span data-stu-id="318b6-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="318b6-115">Puede combinar las opciones especificadas en la línea de comandos con las opciones especificadas en uno o varios archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="318b6-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="318b6-116">El compilador procesa las opciones de comando a medida que las encuentra.</span><span class="sxs-lookup"><span data-stu-id="318b6-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="318b6-117">Por lo tanto, los argumentos de la línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="318b6-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="318b6-118">Por el contrario, las opciones de un archivo de respuesta invalidan las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="318b6-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="318b6-119">Visual Basic proporciona el archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="318b6-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="318b6-120">El archivo Vbc. rsp se incluye de forma predeterminada a menos que se use la opción `-noconfig`.</span><span class="sxs-lookup"><span data-stu-id="318b6-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="318b6-121">Para obtener más información, vea [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="318b6-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="318b6-122">La opción `@` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="318b6-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="318b6-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="318b6-123">Example</span></span>  
 <span data-ttu-id="318b6-124">Las líneas siguientes proceden de un archivo de respuesta de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="318b6-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="318b6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="318b6-125">Example</span></span>  
 <span data-ttu-id="318b6-126">En el ejemplo siguiente se muestra cómo usar la opción `@` con el archivo de respuesta denominado `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="318b6-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="318b6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="318b6-127">See also</span></span>

- [<span data-ttu-id="318b6-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="318b6-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="318b6-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="318b6-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="318b6-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="318b6-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
