---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 05/30/2018
ms.openlocfilehash: 3fdb5443d6d0cfbe1e7e88bc824cbb930f211260
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451186"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="cedc2-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="cedc2-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cedc2-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="cedc2-104">Name</span></span>

<span data-ttu-id="cedc2-105">`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="cedc2-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cedc2-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="cedc2-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="cedc2-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cedc2-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="cedc2-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cedc2-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="cedc2-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cedc2-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="cedc2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cedc2-110">Description</span></span>

<span data-ttu-id="cedc2-111">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="cedc2-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cedc2-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="cedc2-113">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="cedc2-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="cedc2-114">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="cedc2-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="cedc2-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="cedc2-115">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="cedc2-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cedc2-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cedc2-117">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cedc2-118">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="cedc2-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cedc2-119">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cedc2-120">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cedc2-121">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cedc2-122">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cedc2-123">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cedc2-124">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cedc2-125">Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cedc2-126">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cedc2-126">Execute tests in parallel.</span></span> <span data-ttu-id="cedc2-127">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="cedc2-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cedc2-128">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="cedc2-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cedc2-129">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="cedc2-129">Run tests that match the given expression.</span></span> <span data-ttu-id="cedc2-130">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cedc2-131">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cedc2-132">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="cedc2-132">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cedc2-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cedc2-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cedc2-134">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="cedc2-135">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cedc2-136">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cedc2-137">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cedc2-138">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cedc2-139">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cedc2-140">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="cedc2-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cedc2-141">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cedc2-142">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="cedc2-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cedc2-143">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="cedc2-144">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="cedc2-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="cedc2-145">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="cedc2-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cedc2-146">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cedc2-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="cedc2-147">Ejecuta las pruebas en un proceso aislado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="cedc2-148">De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.</span><span class="sxs-lookup"><span data-stu-id="cedc2-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="cedc2-149">Lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="cedc2-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="cedc2-150">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="cedc2-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cedc2-151">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="cedc2-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cedc2-152">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="cedc2-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cedc2-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cedc2-154">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cedc2-155">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="cedc2-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cedc2-156">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cedc2-157">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cedc2-158">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cedc2-159">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cedc2-160">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cedc2-161">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cedc2-162">Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cedc2-163">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cedc2-163">Execute tests in parallel.</span></span> <span data-ttu-id="cedc2-164">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="cedc2-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cedc2-165">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="cedc2-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cedc2-166">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="cedc2-166">Run tests that match the given expression.</span></span> <span data-ttu-id="cedc2-167">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cedc2-168">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cedc2-169">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="cedc2-169">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cedc2-170">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cedc2-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cedc2-171">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="cedc2-172">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cedc2-173">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cedc2-174">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cedc2-175">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cedc2-176">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cedc2-177">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="cedc2-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cedc2-178">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cedc2-179">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="cedc2-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cedc2-180">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="cedc2-181">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="cedc2-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cedc2-182">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="cedc2-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cedc2-183">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="cedc2-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cedc2-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cedc2-185">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cedc2-186">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="cedc2-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cedc2-187">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cedc2-188">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cedc2-189">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cedc2-190">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cedc2-191">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cedc2-192">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cedc2-193">Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cedc2-194">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cedc2-194">Execute tests in parallel.</span></span> <span data-ttu-id="cedc2-195">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="cedc2-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cedc2-196">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="cedc2-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cedc2-197">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="cedc2-197">Run tests that match the given expression.</span></span> <span data-ttu-id="cedc2-198">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cedc2-199">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cedc2-200">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="cedc2-200">Parenthesis `()` are used to group subexpressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cedc2-201">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cedc2-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cedc2-202">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="cedc2-203">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cedc2-204">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="cedc2-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cedc2-205">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cedc2-206">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cedc2-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cedc2-207">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cedc2-208">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="cedc2-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cedc2-209">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cedc2-210">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="cedc2-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cedc2-211">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cedc2-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="cedc2-212">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="cedc2-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cedc2-213">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="cedc2-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cedc2-214">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="cedc2-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cedc2-215">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cedc2-215">Examples</span></span>

<span data-ttu-id="cedc2-216">Ejecutar pruebas en `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="cedc2-217">Ejecutar pruebas en `mytestproject.dll`, exportando a carpeta personalizada con nombre personalizado:</span><span class="sxs-lookup"><span data-stu-id="cedc2-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="cedc2-218">Ejecutar pruebas en `mytestproject.dll` y `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="cedc2-219">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="cedc2-220">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="cedc2-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
