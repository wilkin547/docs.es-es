---
description: Otras opciones del compilador de C#. Estas opciones proporcionan opciones generales para el compilador.
title: Opciones del compilador de C# que no encajan en otras categorías
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- ResponseFiles compiler option [C#]
- NoLogo compiler option [C#]
- NoConfig compiler option [C#]
ms.openlocfilehash: ec7d9c3685c9acb5ca3cda28aca55abb26b836cf
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482477"
---
# <a name="miscellaneous-c-compiler-options"></a><span data-ttu-id="55603-104">Otras opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="55603-104">Miscellaneous C# Compiler Options</span></span>

<span data-ttu-id="55603-105">Las opciones siguientes controlan distintos comportamientos del compilador.</span><span class="sxs-lookup"><span data-stu-id="55603-105">The following options control miscellaneous compiler behavior.</span></span> <span data-ttu-id="55603-106">La nueva sintaxis de MSBuild se muestra en **negrita**.</span><span class="sxs-lookup"><span data-stu-id="55603-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="55603-107">La sintaxis de *csc.exe* anterior se muestra en `code style`.</span><span class="sxs-lookup"><span data-stu-id="55603-107">The older *csc.exe* syntax is shown in `code style`.</span></span>

- <span data-ttu-id="55603-108">**ResponseFiles** / `-@`: se lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="55603-108">**ResponseFiles** / `-@`: Read response file for more options.</span></span>
- <span data-ttu-id="55603-109">**NoLogo** / `-nologo`: se suprime el mensaje de copyright del compilador.</span><span class="sxs-lookup"><span data-stu-id="55603-109">**NoLogo** / `-nologo` : Suppress compiler copyright message.</span></span>
- <span data-ttu-id="55603-110">**NoConfig** / `-noconfig`: no se incluye el archivo *CSC.RSP* de forma automática.</span><span class="sxs-lookup"><span data-stu-id="55603-110">**NoConfig** / `-noconfig`: Don't auto include *CSC.RSP* file.</span></span>

## <a name="responsefiles"></a><span data-ttu-id="55603-111">ResponseFiles</span><span class="sxs-lookup"><span data-stu-id="55603-111">ResponseFiles</span></span>

<span data-ttu-id="55603-112">La opción **ResponseFiles** le permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.</span><span class="sxs-lookup"><span data-stu-id="55603-112">The **ResponseFiles** option lets you specify a file that contains compiler options and source code files to compile.</span></span>

```xml
<ResponseFiles>response_file</ResponseFiles>
```

<span data-ttu-id="55603-113">`response_file` especifica el archivo en el que se enumeran las opciones del compilador o los archivos de código fuente que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="55603-113">The `response_file` specifies the file that lists compiler options or source code files to compile.</span></span> <span data-ttu-id="55603-114">El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubieran especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="55603-114">The compiler options and source code files will be processed by the compiler as if they had been specified on the command line.</span></span> <span data-ttu-id="55603-115">Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="55603-115">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="55603-116">En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="55603-116">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="55603-117">Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias).</span><span class="sxs-lookup"><span data-stu-id="55603-117">A single compiler option specification must appear on one line (can't span multiple lines).</span></span> <span data-ttu-id="55603-118">Los archivos de respuesta pueden tener comentarios que comiencen con el símbolo #.</span><span class="sxs-lookup"><span data-stu-id="55603-118">Response files can have comments that begin with the # symbol.</span></span> <span data-ttu-id="55603-119">Especificar opciones del compilador desde un archivo de respuesta es igual que enviar esos comandos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="55603-119">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="55603-120">El compilador procesa las opciones de comando a medida que se leen.</span><span class="sxs-lookup"><span data-stu-id="55603-120">The compiler processes the command options as they're read.</span></span> <span data-ttu-id="55603-121">Los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="55603-121">Command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="55603-122">Por el contrario, las opciones en un archivo de respuesta reemplazarán las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="55603-122">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span> <span data-ttu-id="55603-123">C# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe.</span><span class="sxs-lookup"><span data-stu-id="55603-123">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="55603-124">Para obtener más información sobre el formato de archivo de respuesta, vea [**NoConfig**](#noconfig).</span><span class="sxs-lookup"><span data-stu-id="55603-124">For more information about the response file format, see [**NoConfig**](#noconfig).</span></span> <span data-ttu-id="55603-125">No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="55603-125">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span> <span data-ttu-id="55603-126">Estas son algunas líneas de un archivo de respuesta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="55603-126">The following are a few lines from a sample response file:</span></span>

```console
# build the first output file
-target:exe -out:MyExe.exe source1.cs source2.cs
```

## <a name="nologo"></a><span data-ttu-id="55603-127">NoLogo</span><span class="sxs-lookup"><span data-stu-id="55603-127">NoLogo</span></span>

<span data-ttu-id="55603-128">La opción **NoLogo** suprime la presentación del banner de inicio de sesión cuando se inicia el compilador y muestra mensajes informativos durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="55603-128">The **NoLogo** option suppresses display of the sign-on banner when the compiler starts up and display of informational messages during compiling.</span></span>

```xml
<NoLogo>true</NoLogo>
```

## <a name="noconfig"></a><span data-ttu-id="55603-129">NoConfig</span><span class="sxs-lookup"><span data-stu-id="55603-129">NoConfig</span></span>

<span data-ttu-id="55603-130">La opción **NoConfig** indica al compilador que no realice la compilación con el archivo *csc.rsp*.</span><span class="sxs-lookup"><span data-stu-id="55603-130">The **NoConfig** option tells the compiler not to compile with the *csc.rsp* file.</span></span>

```xml
<NoConfig>true</NoConfig>
```

<span data-ttu-id="55603-131">El archivo *csc.rsp* hace referencia a todos los ensamblados incluidos en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="55603-131">The *csc.rsp* file references all the assemblies shipped with .NET Framework.</span></span> <span data-ttu-id="55603-132">Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="55603-132">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span> <span data-ttu-id="55603-133">Es posible modificar el archivo *csc.rsp* y especificar opciones del compilador adicionales que se deban incluir en todas las compilaciones.</span><span class="sxs-lookup"><span data-stu-id="55603-133">You can modify the *csc.rsp* file and specify additional compiler options that should be included in every compilation.</span></span> <span data-ttu-id="55603-134">Si no quiere que el compilador busque y use la configuración del archivo *csc.rsp*, especifique **NoConfig**.</span><span class="sxs-lookup"><span data-stu-id="55603-134">If you don't want the compiler to look for and use the settings in the *csc.rsp* file, specify **NoConfig**.</span></span> <span data-ttu-id="55603-135">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="55603-135">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>
