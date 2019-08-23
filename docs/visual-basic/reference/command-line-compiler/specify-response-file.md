---
title: '@ (Especificar archivo de respuesta, Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: b84d50334e56305c27c5c0bc54578ba871a28365
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937292"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="e6685-102">@ (Especificar archivo de respuesta, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6685-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="e6685-103">Especifica un archivo que contiene las opciones del compilador y los archivos de código fuente que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="e6685-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6685-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6685-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6685-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e6685-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="e6685-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e6685-106">Required.</span></span> <span data-ttu-id="e6685-107">Archivo que muestra las opciones del compilador o los archivos de código fuente que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="e6685-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="e6685-108">Escriba el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="e6685-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6685-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6685-109">Remarks</span></span>  
 <span data-ttu-id="e6685-110">El compilador procesa las opciones del compilador y los archivos de código fuente especificados en un archivo de respuesta como si hubieran sido especificados en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6685-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="e6685-111">Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como las siguientes.</span><span class="sxs-lookup"><span data-stu-id="e6685-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="e6685-112">En un archivo de respuesta, pueden aparecer varias opciones del compilador y archivos de código fuente en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="e6685-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="e6685-113">Una única especificación de opción de compilador debe aparecer en una línea (no puede abarcar varias líneas).</span><span class="sxs-lookup"><span data-stu-id="e6685-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="e6685-114">Los archivos de respuesta pueden tener comentarios que comienzan `#` por el símbolo.</span><span class="sxs-lookup"><span data-stu-id="e6685-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="e6685-115">Puede combinar las opciones especificadas en la línea de comandos con las opciones especificadas en uno o varios archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e6685-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="e6685-116">El compilador procesa las opciones de comando a medida que las encuentra.</span><span class="sxs-lookup"><span data-stu-id="e6685-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="e6685-117">Por lo tanto, los argumentos de la línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e6685-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="e6685-118">Por el contrario, las opciones de un archivo de respuesta invalidan las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e6685-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="e6685-119">Visual Basic proporciona el archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="e6685-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="e6685-120">El archivo Vbc. rsp se incluye de forma predeterminada a `-noconfig` menos que se use la opción.</span><span class="sxs-lookup"><span data-stu-id="e6685-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="e6685-121">Para obtener más información, vea [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="e6685-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6685-122">La `@` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6685-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6685-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6685-123">Example</span></span>  
 <span data-ttu-id="e6685-124">Las líneas siguientes proceden de un archivo de respuesta de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e6685-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="e6685-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6685-125">Example</span></span>  
 <span data-ttu-id="e6685-126">En el ejemplo siguiente se muestra cómo usar `@` la opción con el archivo de `File1.rsp`respuesta denominado.</span><span class="sxs-lookup"><span data-stu-id="e6685-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6685-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6685-127">See also</span></span>

- [<span data-ttu-id="e6685-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6685-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e6685-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="e6685-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="e6685-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6685-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
