---
description: Más información sobre @ (especificar archivo de respuesta) (Visual Basic)
title: '@ (especificar archivo de respuesta)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 7a28be0d0bf6da177d9cfe85ecdb40eccf8a339f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473919"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="53022-103">@ (Especificar archivo de respuesta, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53022-103">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="53022-104">Especifica un archivo que contiene opciones del compilador y archivos de código fuente para compilar.</span><span class="sxs-lookup"><span data-stu-id="53022-104">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="53022-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53022-105">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="53022-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="53022-106">Arguments</span></span>

`response_file`  
<span data-ttu-id="53022-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="53022-107">Required.</span></span> <span data-ttu-id="53022-108">Archivo que enumera las opciones del compilador o los archivos de código fuente que se compilarán.</span><span class="sxs-lookup"><span data-stu-id="53022-108">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="53022-109">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="53022-109">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="53022-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53022-110">Remarks</span></span>

<span data-ttu-id="53022-111">El compilador procesa las opciones del compilador y los archivos de código fuente especificados en un archivo de respuesta como si se hubieran especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="53022-111">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="53022-112">Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como aquí.</span><span class="sxs-lookup"><span data-stu-id="53022-112">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="53022-113">En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="53022-113">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="53022-114">Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias líneas).</span><span class="sxs-lookup"><span data-stu-id="53022-114">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="53022-115">Los archivos de respuesta pueden tener comentarios que comiencen por el símbolo `#`.</span><span class="sxs-lookup"><span data-stu-id="53022-115">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="53022-116">Las opciones especificadas en la línea de comandos se pueden combinar con las opciones especificadas en uno o varios archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="53022-116">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="53022-117">El compilador procesa las opciones de comando a medida que las va encontrando.</span><span class="sxs-lookup"><span data-stu-id="53022-117">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="53022-118">Por tanto, los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="53022-118">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="53022-119">Por el contrario, las opciones en un archivo de respuesta reemplazan las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="53022-119">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="53022-120">Visual Basic proporciona el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="53022-120">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="53022-121">El archivo Vbc.rsp se incluye de forma predeterminada, a menos que se use la opción `-noconfig`.</span><span class="sxs-lookup"><span data-stu-id="53022-121">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="53022-122">Para más información, vea [-noconfig](noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="53022-122">For more information, see [-noconfig](noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53022-123">La opción `@` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="53022-123">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="53022-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53022-124">Example</span></span>

<span data-ttu-id="53022-125">Las siguientes líneas pertenecen a un archivo de respuesta de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="53022-125">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="53022-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53022-126">Example</span></span>

<span data-ttu-id="53022-127">En el siguiente ejemplo se muestra cómo usar la opción `@` junto con el archivo de respuesta `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="53022-127">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="53022-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="53022-128">See also</span></span>

- [<span data-ttu-id="53022-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53022-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="53022-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="53022-130">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="53022-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="53022-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
