---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975399"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="0c590-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="0c590-103">dotnet vstest</span></span>

<span data-ttu-id="0c590-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0c590-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c590-105">El comando `dotnet vstest` se sustituye por `dotnet test`, que ahora se puede usar para ejecutar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0c590-105">The `dotnet vstest` command is superseded by `dotnet test`, which can now be used to run assemblies.</span></span> <span data-ttu-id="0c590-106">Vea [`dotnet test`](dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="0c590-106">See [`dotnet test`](dotnet-test.md).</span></span>

## <a name="name"></a><span data-ttu-id="0c590-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0c590-107">Name</span></span>

<span data-ttu-id="0c590-108">`dotnet-vstest`: permite ejecutar pruebas a partir de los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="0c590-108">`dotnet-vstest` - Runs tests from the specified assemblies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c590-109">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0c590-109">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="0c590-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c590-110">Description</span></span>

<span data-ttu-id="0c590-111">El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.</span><span class="sxs-lookup"><span data-stu-id="0c590-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="0c590-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c590-112">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="0c590-113">Ejecutar pruebas desde los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="0c590-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="0c590-114">Separar varios nombres de ensamblado de prueba con espacios.</span><span class="sxs-lookup"><span data-stu-id="0c590-114">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="0c590-115">Se admite caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="0c590-115">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="0c590-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c590-116">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="0c590-117">Ejecuta las pruebas en el modo de culpabilidad.</span><span class="sxs-lookup"><span data-stu-id="0c590-117">Runs the tests in blame mode.</span></span> <span data-ttu-id="0c590-118">Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee.</span><span class="sxs-lookup"><span data-stu-id="0c590-118">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="0c590-119">Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0c590-119">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="0c590-120">Permite registros detallados para la plataforma de prueba.</span><span class="sxs-lookup"><span data-stu-id="0c590-120">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="0c590-121">Los registros se escriben en el archivo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="0c590-121">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="0c590-122">Identificar la versión de .NET Framework usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-122">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="0c590-123">Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="0c590-123">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="0c590-124">Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="0c590-124">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="0c590-125">Ejecuta las pruebas en un proceso aislado.</span><span class="sxs-lookup"><span data-stu-id="0c590-125">Runs the tests in an isolated process.</span></span> <span data-ttu-id="0c590-126">De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.</span><span class="sxs-lookup"><span data-stu-id="0c590-126">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="0c590-127">Muestra todas las pruebas detectadas del contenedor de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="0c590-127">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="0c590-128">Especifica un registrador para resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-128">Specify a logger for test results.</span></span>

  - <span data-ttu-id="0c590-129">Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="0c590-129">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="0c590-130">Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`.</span><span class="sxs-lookup"><span data-stu-id="0c590-130">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="0c590-131">Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado.</span><span class="sxs-lookup"><span data-stu-id="0c590-131">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="0c590-132">Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-132">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="0c590-133">Ejecuta pruebas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="0c590-133">Run tests in parallel.</span></span> <span data-ttu-id="0c590-134">De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="0c590-134">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="0c590-135">Especifique un número explícito de núcleos mediante la configuración de la propiedad `MaxCpuCount` en el nodo `RunConfiguration` del archivo *runsettings*.</span><span class="sxs-lookup"><span data-stu-id="0c590-135">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="0c590-136">Id. de proceso del proceso principal responsable de iniciar el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="0c590-136">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="0c590-137">Identificar la arquitectura de la plataforma usada en la ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-137">Target platform architecture used for test execution.</span></span> <span data-ttu-id="0c590-138">Valores válidos son `x86`, `x64` y `ARM`.</span><span class="sxs-lookup"><span data-stu-id="0c590-138">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="0c590-139">Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="0c590-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="0c590-140">Si no existe, el directorio de los resultados de la prueba se creará en la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="0c590-140">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="0c590-141">Configuración que se usará al ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-141">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="0c590-142">Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="0c590-142">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="0c590-143">Ejecuta pruebas que coinciden con la expresión dada.</span><span class="sxs-lookup"><span data-stu-id="0c590-143">Run tests that match the given expression.</span></span> <span data-ttu-id="0c590-144">`<EXPRESSION>` tiene el formato `<property>Operator<value>[|&<EXPRESSION>]`, donde Operator es `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="0c590-144">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="0c590-145">El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="0c590-145">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="0c590-146">Los paréntesis `()` se usan para agrupar subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="0c590-146">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="0c590-147">Para obtener más información, vea [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="0c590-147">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="0c590-148">Ejecuta las pruebas con nombres que coinciden con los</span><span class="sxs-lookup"><span data-stu-id="0c590-148">Run tests with names that match the provided values.</span></span> <span data-ttu-id="0c590-149">Separar varios valores con comas.</span><span class="sxs-lookup"><span data-stu-id="0c590-149">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="0c590-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0c590-150">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="0c590-151">Lee el archivo de respuesta para ver más opciones.</span><span class="sxs-lookup"><span data-stu-id="0c590-151">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="0c590-152">Especifica argumentos adicionales para pasar al adaptador.</span><span class="sxs-lookup"><span data-stu-id="0c590-152">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="0c590-153">Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="0c590-153">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="0c590-154">Use un espacio para separar varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="0c590-154">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="0c590-155">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0c590-155">Examples</span></span>

<span data-ttu-id="0c590-156">Ejecución de pruebas en *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="0c590-156">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="0c590-157">Ejecución de pruebas en *mytestproject.dll*, exportación a una carpeta personalizada con nombre personalizado:</span><span class="sxs-lookup"><span data-stu-id="0c590-157">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="0c590-158">Ejecución de pruebas en *mytestproject.dll* y *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="0c590-158">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="0c590-159">Ejecutar pruebas `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="0c590-159">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="0c590-160">Ejecutar pruebas `TestMethod1` y `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="0c590-160">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="0c590-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c590-161">See also</span></span>

- [<span data-ttu-id="0c590-162">Opciones de la línea de comandos para VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="0c590-162">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
