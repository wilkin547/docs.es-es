---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
author: mairaw
ms.date: 05/30/2018
ms.openlocfilehash: 45fda3b34d2649bc6f20cf3f35c65277a9a53cec
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300032"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="dfbbc-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="dfbbc-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="dfbbc-104">nombre</span><span class="sxs-lookup"><span data-stu-id="dfbbc-104">Name</span></span>

<span data-ttu-id="dfbbc-105">`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dfbbc-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="dfbbc-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="dfbbc-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="dfbbc-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="dfbbc-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="dfbbc-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfbbc-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfbbc-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="dfbbc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfbbc-110">Description</span></span>

<span data-ttu-id="dfbbc-111">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="dfbbc-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfbbc-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="dfbbc-113">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="dfbbc-114">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="dfbbc-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="dfbbc-115">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="dfbbc-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="dfbbc-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="dfbbc-117">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="dfbbc-118">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="dfbbc-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="dfbbc-119">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="dfbbc-120">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="dfbbc-121">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="dfbbc-122">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="dfbbc-123">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="dfbbc-124">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="dfbbc-125">Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="dfbbc-126">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-126">Execute tests in parallel.</span></span> <span data-ttu-id="dfbbc-127">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="dfbbc-128">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="dfbbc-129">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-129">Run tests that match the given expression.</span></span> <span data-ttu-id="dfbbc-130">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="dfbbc-131">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="dfbbc-132">Los paréntesis `()` se usan para agrupar expresiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-132">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="dfbbc-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="dfbbc-134">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="dfbbc-135">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="dfbbc-136">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="dfbbc-137">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="dfbbc-138">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="dfbbc-139">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="dfbbc-140">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="dfbbc-141">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="dfbbc-142">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="dfbbc-143">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="dfbbc-144">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="dfbbc-145">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="dfbbc-146">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="dfbbc-147">Ejecuta las pruebas en un proceso aislado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="dfbbc-148">De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="dfbbc-149">Lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="dfbbc-150">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="dfbbc-151">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="dfbbc-152">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="dfbbc-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="dfbbc-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="dfbbc-154">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="dfbbc-155">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="dfbbc-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="dfbbc-156">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="dfbbc-157">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="dfbbc-158">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="dfbbc-159">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="dfbbc-160">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="dfbbc-161">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="dfbbc-162">Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="dfbbc-163">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-163">Execute tests in parallel.</span></span> <span data-ttu-id="dfbbc-164">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="dfbbc-165">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="dfbbc-166">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-166">Run tests that match the given expression.</span></span> <span data-ttu-id="dfbbc-167">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="dfbbc-168">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="dfbbc-169">Los paréntesis `()` se usan para agrupar expresiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-169">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="dfbbc-170">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="dfbbc-171">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="dfbbc-172">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="dfbbc-173">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="dfbbc-174">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="dfbbc-175">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="dfbbc-176">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="dfbbc-177">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="dfbbc-178">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="dfbbc-179">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="dfbbc-180">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="dfbbc-181">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="dfbbc-182">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="dfbbc-183">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfbbc-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfbbc-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="dfbbc-185">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="dfbbc-186">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="dfbbc-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="dfbbc-187">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="dfbbc-188">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="dfbbc-189">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="dfbbc-190">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="dfbbc-191">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="dfbbc-192">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="dfbbc-193">Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="dfbbc-194">Ejecutar pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-194">Execute tests in parallel.</span></span> <span data-ttu-id="dfbbc-195">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="dfbbc-196">Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="dfbbc-197">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-197">Run tests that match the given expression.</span></span> <span data-ttu-id="dfbbc-198">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="dfbbc-199">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="dfbbc-200">Los paréntesis `()` se usan para agrupar expresiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-200">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="dfbbc-201">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="dfbbc-202">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="dfbbc-203">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="dfbbc-204">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="dfbbc-205">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="dfbbc-206">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="dfbbc-207">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="dfbbc-208">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="dfbbc-209">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="dfbbc-210">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="dfbbc-211">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="dfbbc-212">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="dfbbc-213">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="dfbbc-214">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="dfbbc-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="dfbbc-215">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dfbbc-215">Examples</span></span>

<span data-ttu-id="dfbbc-216">Ejecutar pruebas en `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="dfbbc-217">Ejecutar pruebas en `mytestproject.dll`, exportando a carpeta personalizada con nombre personalizado:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="dfbbc-218">Ejecutar pruebas en `mytestproject.dll` y `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="dfbbc-219">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="dfbbc-220">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="dfbbc-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
