---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156938"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="2c0d6-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="2c0d6-103">dotnet vstest</span></span>

<span data-ttu-id="2c0d6-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2c0d6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2c0d6-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="2c0d6-105">Name</span></span>

<span data-ttu-id="2c0d6-106">`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2c0d6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="2c0d6-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="2c0d6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c0d6-108">Description</span></span>

<span data-ttu-id="2c0d6-109">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="2c0d6-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2c0d6-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="2c0d6-111">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="2c0d6-112">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="2c0d6-113">Se admite caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="2c0d6-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="2c0d6-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="2c0d6-115">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="2c0d6-116">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="2c0d6-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="2c0d6-117">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="2c0d6-118">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="2c0d6-119">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="2c0d6-120">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="2c0d6-121">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="2c0d6-122">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="2c0d6-123">Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="2c0d6-124">Ejecuta pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-124">Run tests in parallel.</span></span> <span data-ttu-id="2c0d6-125">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="2c0d6-126">Especifique un número explícito de núcleos mediante la configuración de la propiedad `MaxCpuCount` en el nodo `RunConfiguration` del archivo *runsettings*.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="2c0d6-127">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-127">Run tests that match the given expression.</span></span> <span data-ttu-id="2c0d6-128">`<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="2c0d6-129">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="2c0d6-130">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="2c0d6-131">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="2c0d6-132">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="2c0d6-133">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="2c0d6-134">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="2c0d6-135">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="2c0d6-136">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="2c0d6-137">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="2c0d6-138">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="2c0d6-139">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="2c0d6-140">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="2c0d6-141">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="2c0d6-142">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="2c0d6-143">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="2c0d6-144">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="2c0d6-145">Ejecuta las pruebas en un proceso aislado.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="2c0d6-146">De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="2c0d6-147">Lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="2c0d6-148">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="2c0d6-149">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="2c0d6-150">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="2c0d6-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="2c0d6-151">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2c0d6-151">Examples</span></span>

<span data-ttu-id="2c0d6-152">Ejecución de pruebas en *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="2c0d6-153">Ejecución de pruebas en *mytestproject.dll*, exportación a una carpeta personalizada con nombre personalizado:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="2c0d6-154">Ejecución de pruebas en *mytestproject.dll* y *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="2c0d6-155">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="2c0d6-156">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="2c0d6-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
