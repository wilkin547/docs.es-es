---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793544"
---
# <a name="-bugreport"></a><span data-ttu-id="6d7e0-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="6d7e0-102">-bugreport</span></span>

<span data-ttu-id="6d7e0-103">Crea un archivo que se puede usar al archivar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d7e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d7e0-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="6d7e0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6d7e0-105">Arguments</span></span>

|<span data-ttu-id="6d7e0-106">Término</span><span class="sxs-lookup"><span data-stu-id="6d7e0-106">Term</span></span>|<span data-ttu-id="6d7e0-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="6d7e0-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="6d7e0-108">Obligatoria.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-108">Required.</span></span> <span data-ttu-id="6d7e0-109">Nombre del archivo que contendrá el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="6d7e0-110">Escriba el nombre de archivo entre comillas ("") si el nombre contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6d7e0-111">Notas</span><span class="sxs-lookup"><span data-stu-id="6d7e0-111">Remarks</span></span>

<span data-ttu-id="6d7e0-112">La siguiente información se agrega a `file`:</span><span class="sxs-lookup"><span data-stu-id="6d7e0-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="6d7e0-113">Una copia de todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="6d7e0-114">Una lista de las opciones del compilador utilizadas en la compilación.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="6d7e0-115">Información de versión sobre el compilador, el Common Language Runtime y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="6d7e0-116">Resultados del compilador, si los hay.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-116">Compiler output, if any.</span></span>

- <span data-ttu-id="6d7e0-117">Una descripción del problema, para el que se le solicita.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="6d7e0-118">Una descripción de cómo cree que el problema debe corregirse, para lo que se le solicita.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="6d7e0-119">Dado que una copia de todos los archivos de código fuente se incluye en `file`, puede que desee reproducir el defecto de código (sospechoso) en el programa más corto posible.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d7e0-120">La opción `-bugreport` genera un archivo que contiene información potencialmente confidencial.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="6d7e0-121">Esto incluye la hora actual, la versión del compilador, la versión .NET Framework, la versión del sistema operativo, el nombre de usuario, los argumentos de línea de comandos con los que se ejecutó el compilador, todo el código fuente y el formato binario de cualquier ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="6d7e0-122">Se puede tener acceso a esta opción si se especifican las opciones de línea de comandos en el archivo Web. config para una compilación del lado servidor de una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="6d7e0-123">Para evitarlo, modifique el archivo Machine. config para que no permita a los usuarios compilar en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="6d7e0-124">Si esta opción se usa con `-errorreport:prompt`, `-errorreport:queue`o `-errorreport:send`y la aplicación encuentra un error interno del compilador, la información de `file` se envía a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="6d7e0-125">Esa información ayudará a los ingenieros de Microsoft a identificar la causa del error y puede ayudar a mejorar la próxima versión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="6d7e0-126">De forma predeterminada, no se envía información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="6d7e0-127">Sin embargo, al compilar una aplicación mediante `-errorreport:queue`, que está habilitada de forma predeterminada, la aplicación recopila sus informes de errores.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="6d7e0-128">A continuación, cuando el administrador del equipo inicia sesión, el sistema de informes de errores muestra una ventana emergente que permite al administrador reenviar a Microsoft los informes de errores que se produjeron desde el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="6d7e0-129">La opción `-bugreport` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="6d7e0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d7e0-130">Example</span></span>

<span data-ttu-id="6d7e0-131">En el ejemplo siguiente se compila *T2. VB* y se coloca toda la información de informes de errores en el archivo *Problem. txt*.</span><span class="sxs-lookup"><span data-stu-id="6d7e0-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="6d7e0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d7e0-132">See also</span></span>

- [<span data-ttu-id="6d7e0-133">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d7e0-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6d7e0-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d7e0-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="6d7e0-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="6d7e0-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="6d7e0-136">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d7e0-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="6d7e0-137">[trustLevel (elemento) para securityPolicy (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6d7e0-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
