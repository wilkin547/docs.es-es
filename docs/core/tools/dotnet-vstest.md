---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463286"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="dfa03-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="dfa03-103">dotnet vstest</span></span>

<span data-ttu-id="dfa03-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="dfa03-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="dfa03-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="dfa03-105">Name</span></span>

<span data-ttu-id="dfa03-106">`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="dfa03-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dfa03-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="dfa03-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="dfa03-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfa03-108">Description</span></span>

<span data-ttu-id="dfa03-109">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="dfa03-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfa03-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="dfa03-111">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="dfa03-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="dfa03-112">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="dfa03-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="dfa03-113">Se admite caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="dfa03-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="dfa03-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="dfa03-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="dfa03-115">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="dfa03-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="dfa03-116">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="dfa03-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="dfa03-117">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dfa03-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="dfa03-118">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="dfa03-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="dfa03-119">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="dfa03-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="dfa03-120">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="dfa03-121">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="dfa03-122">Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="dfa03-123">Ejecuta las pruebas en un proceso aislado.</span><span class="sxs-lookup"><span data-stu-id="dfa03-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="dfa03-124">De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.</span><span class="sxs-lookup"><span data-stu-id="dfa03-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="dfa03-125">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="dfa03-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="dfa03-126">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="dfa03-127">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="dfa03-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="dfa03-128">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="dfa03-129">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="dfa03-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="dfa03-130">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="dfa03-131">Ejecuta pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfa03-131">Run tests in parallel.</span></span> <span data-ttu-id="dfa03-132">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="dfa03-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="dfa03-133">Especifique un número explícito de núcleos mediante la configuración de la propiedad `MaxCpuCount` en el nodo `RunConfiguration` del archivo *runsettings*.</span><span class="sxs-lookup"><span data-stu-id="dfa03-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="dfa03-134">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dfa03-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="dfa03-135">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="dfa03-136">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="dfa03-137">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="dfa03-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="dfa03-138">Si no existe, el directorio de los resultados de la prueba se creará en la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="dfa03-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="dfa03-139">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="dfa03-140">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="dfa03-141">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="dfa03-141">Run tests that match the given expression.</span></span> <span data-ttu-id="dfa03-142">`<EXPRESSION>` tiene el formato `<property>Operator<value>[|&<EXPRESSION>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="dfa03-143">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="dfa03-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="dfa03-144">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="dfa03-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="dfa03-145">Para obtener más información, vea [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="dfa03-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="dfa03-146">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="dfa03-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="dfa03-147">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="dfa03-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="dfa03-148">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfa03-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="dfa03-149">Lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="dfa03-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="dfa03-150">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="dfa03-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="dfa03-151">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="dfa03-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="dfa03-152">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="dfa03-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="dfa03-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dfa03-153">Examples</span></span>

<span data-ttu-id="dfa03-154">Ejecución de pruebas en *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="dfa03-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="dfa03-155">Ejecución de pruebas en *mytestproject.dll*, exportación a una carpeta personalizada con nombre personalizado:</span><span class="sxs-lookup"><span data-stu-id="dfa03-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="dfa03-156">Ejecución de pruebas en *mytestproject.dll* y *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="dfa03-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="dfa03-157">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="dfa03-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="dfa03-158">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="dfa03-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="dfa03-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfa03-159">See also</span></span>

- [<span data-ttu-id="dfa03-160">Opciones de la línea de comandos para VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="dfa03-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
