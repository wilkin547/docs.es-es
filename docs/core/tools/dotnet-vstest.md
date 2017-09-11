---
title: 'Comando dotnet vstest: CLI de .NET Core'
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: c5a7ee0ba306cea641b0ff34f0b521c92bd03719
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-vstest"></a><span data-ttu-id="a5c26-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="a5c26-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a5c26-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="a5c26-104">Name</span></span>

<span data-ttu-id="a5c26-105">`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="a5c26-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a5c26-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="a5c26-106">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="a5c26-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5c26-107">Description</span></span>

<span data-ttu-id="a5c26-108">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas de aplicaciones de interfaz de usuario codificadas y unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-108">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="a5c26-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a5c26-109">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="a5c26-110">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="a5c26-110">Run tests from the specified assemblies.</span></span> <span data-ttu-id="a5c26-111">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="a5c26-111">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="a5c26-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="a5c26-112">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="a5c26-113">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-113">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="a5c26-114">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="a5c26-114">Run tests with names that match the provided values.</span></span> <span data-ttu-id="a5c26-115">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-115">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="a5c26-116">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-116">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="a5c26-117">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-117">Target platform architecture used for test execution.</span></span> <span data-ttu-id="a5c26-118">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="a5c26-118">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="a5c26-119">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-119">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="a5c26-120">Ejemplos de valores válidos son `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Otros valores admitidos son `Framework35`, `Framework40`, `Framework45` y `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="a5c26-120">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="a5c26-121">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="a5c26-121">Execute tests in parallel.</span></span> <span data-ttu-id="a5c26-122">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="a5c26-122">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="a5c26-123">Establecer un número explícito de núcleos con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5c26-123">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="a5c26-124">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="a5c26-124">Run tests that match the given expression.</span></span> <span data-ttu-id="a5c26-125">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="a5c26-125">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="a5c26-126">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="a5c26-126">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="a5c26-127">Los paréntesis `()` se usan para agrupar expresiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="a5c26-127">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="a5c26-128">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="a5c26-128">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="a5c26-129">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-129">Specify a logger for test results.</span></span>  

* <span data-ttu-id="a5c26-130">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="a5c26-130">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="a5c26-131">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="a5c26-131">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="a5c26-132">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="a5c26-132">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="a5c26-133">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a5c26-133">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="a5c26-134">Muestra las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="a5c26-134">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="a5c26-135">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="a5c26-135">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="a5c26-136">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="a5c26-136">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="a5c26-137">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="a5c26-137">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="a5c26-138">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="a5c26-138">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="a5c26-139">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="a5c26-139">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="a5c26-140">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="a5c26-140">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="a5c26-141">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="a5c26-141">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="a5c26-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a5c26-142">Examples</span></span>

<span data-ttu-id="a5c26-143">Ejecutar pruebas en `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="a5c26-143">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="a5c26-144">Ejecutar pruebas en `mytestproject.dll` y `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="a5c26-144">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="a5c26-145">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="a5c26-145">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="a5c26-146">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="a5c26-146">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`

