---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e7b4ebc58b6fe9850b92ef945cb0d715e4369efe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820916"
---
# <a name="-bugreport"></a><span data-ttu-id="778c6-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="778c6-102">-bugreport</span></span>
<span data-ttu-id="778c6-103">Crea un archivo que puede usar cuando se archiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="778c6-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="778c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="778c6-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="778c6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="778c6-105">Arguments</span></span>  
  
|<span data-ttu-id="778c6-106">Término</span><span class="sxs-lookup"><span data-stu-id="778c6-106">Term</span></span>|<span data-ttu-id="778c6-107">Definición</span><span class="sxs-lookup"><span data-stu-id="778c6-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="778c6-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="778c6-108">Required.</span></span> <span data-ttu-id="778c6-109">El nombre del archivo que contendrá el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="778c6-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="778c6-110">Ponga el nombre de archivo entre comillas ("") si el nombre contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="778c6-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="778c6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="778c6-111">Remarks</span></span>  
 <span data-ttu-id="778c6-112">La siguiente información se agrega a `file`:</span><span class="sxs-lookup"><span data-stu-id="778c6-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="778c6-113">Una copia de todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="778c6-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="778c6-114">Una lista de las opciones del compilador utilizadas en la compilación.</span><span class="sxs-lookup"><span data-stu-id="778c6-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="778c6-115">Información de versión sobre su compilador, el common language runtime y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="778c6-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="778c6-116">Resultados del compilador, si los hay.</span><span class="sxs-lookup"><span data-stu-id="778c6-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="778c6-117">Una descripción del problema, para el que se le pedirá.</span><span class="sxs-lookup"><span data-stu-id="778c6-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="778c6-118">Una descripción de cómo cree que el problema debe corregirse para que se le pedirá.</span><span class="sxs-lookup"><span data-stu-id="778c6-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="778c6-119">Dado que una copia de todos los archivos de código fuente se incluye en `file`, que es posible que desee reproducir el defecto de código (sospechado) en el programa más corto posible.</span><span class="sxs-lookup"><span data-stu-id="778c6-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="778c6-120">El `-bugreport` opción genera un archivo que contiene información potencialmente confidencial.</span><span class="sxs-lookup"><span data-stu-id="778c6-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="778c6-121">Esto incluye la hora actual, la versión de compilador [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] versión, versión del sistema operativo, nombre de usuario, los argumentos de línea de comandos con la que se ejecutó el compilador, todo el código fuente y el formato binario de cualquiera al que hace referencia el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="778c6-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="778c6-122">Esta opción puede obtenerse mediante la especificación de opciones de línea de comandos en el archivo Web.config para una compilación de servidor de un [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="778c6-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="778c6-123">Para evitar esto, modifique el archivo Machine.config para impedir que los usuarios realizar la compilación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="778c6-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="778c6-124">Si esta opción se utiliza con `-errorreport:prompt`, `-errorreport:queue`, o `-errorreport:send`, y la aplicación detecta un error interno del compilador, la información de `file` se envía a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="778c6-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="778c6-125">Esta información le ayudará a los ingenieros de Microsoft a identificar la causa del error y puede ayudar a mejorar la próxima versión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="778c6-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="778c6-126">De forma predeterminada, no se envía ninguna información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="778c6-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="778c6-127">Sin embargo, cuando se compila una aplicación mediante el uso de `-errorreport:queue`, que está habilitado de forma predeterminada, la aplicación recopila los informes de errores.</span><span class="sxs-lookup"><span data-stu-id="778c6-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="778c6-128">A continuación, cuando el administrador del equipo inicia sesión, el sistema de informes de errores muestra una ventana emergente que permite al administrador enviar a Microsoft los informes de errores producidos desde el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="778c6-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="778c6-129">El `/bugreport` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="778c6-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="778c6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="778c6-130">Example</span></span>  
 <span data-ttu-id="778c6-131">El ejemplo siguiente se compila `T2.vb` y coloca toda la información de informes de errores en el archivo `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="778c6-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="778c6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="778c6-132">See also</span></span>

- [<span data-ttu-id="778c6-133">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="778c6-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="778c6-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="778c6-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="778c6-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="778c6-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="778c6-136">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="778c6-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="778c6-137">[Elemento trustLevel para securityPolicy (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="778c6-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
