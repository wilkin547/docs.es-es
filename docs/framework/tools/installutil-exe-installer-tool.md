---
title: Installutil.exe (Herramienta Installer)
description: Use Installutil.exe, la herramienta de instalación. Esta herramienta permite instalar o desinstalar recursos de servidor mediante la ejecución de los componentes del instalador en los ensamblados especificados.
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: 0e03a2a7033d3e210727e2eb080140ad87240dba
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259946"
---
# <a name="installutilexe-installer-tool"></a><span data-ttu-id="15d72-104">Installutil.exe (Herramienta Installer)</span><span class="sxs-lookup"><span data-stu-id="15d72-104">Installutil.exe (Installer Tool)</span></span>

<span data-ttu-id="15d72-105">La herramienta de instalación es una utilidad de la línea de comandos que le permite instalar y desinstalar recursos de servidor mediante la ejecución de los componentes del instalador en ensamblados específicos.</span><span class="sxs-lookup"><span data-stu-id="15d72-105">The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing the installer components in specified assemblies.</span></span> <span data-ttu-id="15d72-106">Esta herramienta funciona junto con clases del espacio de nombres <xref:System.Configuration.Install>.</span><span class="sxs-lookup"><span data-stu-id="15d72-106">This tool works in conjunction with classes in the <xref:System.Configuration.Install> namespace.</span></span>

<span data-ttu-id="15d72-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="15d72-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="15d72-108">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="15d72-108">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>

<span data-ttu-id="15d72-109">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15d72-109">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="15d72-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15d72-110">Syntax</span></span>

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a><span data-ttu-id="15d72-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15d72-111">Parameters</span></span>

|<span data-ttu-id="15d72-112">Argumento</span><span class="sxs-lookup"><span data-stu-id="15d72-112">Argument</span></span>|<span data-ttu-id="15d72-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="15d72-113">Description</span></span>|
|--------------|-----------------|
|`assembly`|<span data-ttu-id="15d72-114">Nombre de archivo del ensamblado en el que se ejecutan los componentes del instalador.</span><span class="sxs-lookup"><span data-stu-id="15d72-114">The file name of the assembly in which to execute the installer components.</span></span> <span data-ttu-id="15d72-115">Omita este parámetro si desea especificar el nombre seguro del ensamblado mediante la opción `/AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="15d72-115">Omit this parameter if you want to specify the assembly's strong name by using the `/AssemblyName` option.</span></span>|

<a name="options"></a>

## <a name="options"></a><span data-ttu-id="15d72-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="15d72-116">Options</span></span>

|<span data-ttu-id="15d72-117">Opción</span><span class="sxs-lookup"><span data-stu-id="15d72-117">Option</span></span>|<span data-ttu-id="15d72-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="15d72-118">Description</span></span>|
|------------|-----------------|
|`/h[elp]`<br /><br /> <span data-ttu-id="15d72-119">o bien</span><span class="sxs-lookup"><span data-stu-id="15d72-119">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="15d72-120">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="15d72-120">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="15d72-121">`/help` *assembly*</span><span class="sxs-lookup"><span data-stu-id="15d72-121">`/help` *assembly*</span></span><br /><br /> <span data-ttu-id="15d72-122">o bien</span><span class="sxs-lookup"><span data-stu-id="15d72-122">-or-</span></span><br /><br /> <span data-ttu-id="15d72-123">`/?` *assembly*</span><span class="sxs-lookup"><span data-stu-id="15d72-123">`/?` *assembly*</span></span>|<span data-ttu-id="15d72-124">Muestra opciones adicionales reconocidas por instaladores individuales dentro del ensamblado especificado, junto con la sintaxis y las opciones de los comandos de InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="15d72-124">Displays additional options recognized by individual installers within the specified assembly, along with command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="15d72-125">Esta opción agrega el texto devuelto por la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> de cada componente del instalador al texto de ayuda de InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="15d72-125">This option adds the text returned by each installer component's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property to the help text of InstallUtil.exe.</span></span>|
|<span data-ttu-id="15d72-126">`/AssemblyName` "*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="15d72-126">`/AssemblyName` "*assemblyName*</span></span><br /><br /> <span data-ttu-id="15d72-127">,Version=*major.minor.build.revision*</span><span class="sxs-lookup"><span data-stu-id="15d72-127">,Version=*major.minor.build.revision*</span></span><br /><br /> <span data-ttu-id="15d72-128">,Culture=*locale*</span><span class="sxs-lookup"><span data-stu-id="15d72-128">,Culture=*locale*</span></span><br /><br /> <span data-ttu-id="15d72-129">,PublicKeyToken=*publicKeyToken*"</span><span class="sxs-lookup"><span data-stu-id="15d72-129">,PublicKeyToken=*publicKeyToken*"</span></span>|<span data-ttu-id="15d72-130">Especifica el nombre seguro de un ensamblado, que debe registrarse en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="15d72-130">Specifies the strong name of an assembly, which must be registered in the global assembly cache.</span></span> <span data-ttu-id="15d72-131">El nombre del ensamblado debe ser completo e incluir la versión, la referencia cultural y el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="15d72-131">The assembly name must be fully qualified with the version, culture, and public key token of the assembly.</span></span> <span data-ttu-id="15d72-132">El nombre completo debe ir entre comillas.</span><span class="sxs-lookup"><span data-stu-id="15d72-132">The fully qualified name must be surrounded by quotes.</span></span><br /><br /> <span data-ttu-id="15d72-133">Por ejemplo, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" es un nombre de ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="15d72-133">For example, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" is a fully qualified assembly name.</span></span>|
|<span data-ttu-id="15d72-134">`/InstallStateDir=[` *directoryName* `]`</span><span class="sxs-lookup"><span data-stu-id="15d72-134">`/InstallStateDir=[` *directoryName* `]`</span></span>|<span data-ttu-id="15d72-135">Especifica el directorio del archivo .InstallState que contiene los datos usados para desinstalar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15d72-135">Specifies the directory of the .InstallState file that contains the data used to uninstall the assembly.</span></span> <span data-ttu-id="15d72-136">El directorio predeterminado es el que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15d72-136">The default is the directory that contains the assembly.</span></span>|
|<span data-ttu-id="15d72-137">`/LogFile=`[*filename*]</span><span class="sxs-lookup"><span data-stu-id="15d72-137">`/LogFile=`[*filename*]</span></span>|<span data-ttu-id="15d72-138">Especifica el nombre del archivo de registro donde se graba el progreso de la instalación.</span><span class="sxs-lookup"><span data-stu-id="15d72-138">Specifies the name of the log file where installation progress is recorded.</span></span> <span data-ttu-id="15d72-139">De forma predeterminada, si se omite la opción `/LogFile`, se crea un archivo de registro denominado *assemblyname*.InstallLog.</span><span class="sxs-lookup"><span data-stu-id="15d72-139">By default, if the `/LogFile` option is omitted, a log file named *assemblyname*.InstallLog is created.</span></span> <span data-ttu-id="15d72-140">Si se omite *filename*, no se genera ningún archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="15d72-140">If *filename* is omitted, no log file is generated.</span></span>|
|<span data-ttu-id="15d72-141">`/LogToConsole`={`true`&#124;`false`}</span><span class="sxs-lookup"><span data-stu-id="15d72-141">`/LogToConsole`={`true`&#124;`false`}</span></span>|<span data-ttu-id="15d72-142">Si es `true`, muestra el resultado en la consola.</span><span class="sxs-lookup"><span data-stu-id="15d72-142">If `true`, displays output to the console.</span></span> <span data-ttu-id="15d72-143">Si es `false` (valor predeterminado), el resultado no se muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="15d72-143">If `false` (the default), suppresses output to the console.</span></span>|
|`/ShowCallStack`|<span data-ttu-id="15d72-144">Envía la pila de llamadas al archivo de registro si se produce una excepción en cualquier paso de la instalación.</span><span class="sxs-lookup"><span data-stu-id="15d72-144">Outputs the call stack to the log file if an exception occurs at any point during installation.</span></span>|
|<span data-ttu-id="15d72-145">`/u`[`ninstall`]</span><span class="sxs-lookup"><span data-stu-id="15d72-145">`/u`[`ninstall`]</span></span>|<span data-ttu-id="15d72-146">Desinstala los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="15d72-146">Uninstalls the specified assemblies.</span></span> <span data-ttu-id="15d72-147">A diferencia de las demás opciones, `/u` se aplica a todos los ensamblados con independencia del lugar donde aparezca la opción en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="15d72-147">Unlike the other options, `/u` applies to all assemblies regardless of where the option appears on the command line.</span></span>|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a><span data-ttu-id="15d72-148">Opciones adicionales del instalador</span><span class="sxs-lookup"><span data-stu-id="15d72-148">Additional Installer Options</span></span>

<span data-ttu-id="15d72-149">Los instaladores individuales utilizados en un ensamblado pueden reconocer opciones adicionales a las enumeradas en la sección [Opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="15d72-149">Individual installers used within an assembly may recognize options in addition to those listed in the [Options](#options) section.</span></span> <span data-ttu-id="15d72-150">Para obtener información sobre estas opciones, ejecute InstallUtil.exe con las rutas de acceso de los ensamblados en la línea de comandos junto con la opción `/?` o `/help`.</span><span class="sxs-lookup"><span data-stu-id="15d72-150">To learn about these options, run InstallUtil.exe with the paths of the assemblies on the command line along with the `/?` or `/help` option.</span></span> <span data-ttu-id="15d72-151">Para especificar estas opciones, debe incluirlas en la línea de comandos junto con las opciones reconocidas por InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="15d72-151">To specify these options, you include them on the command line along with the options recognized by InstallUtil.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="15d72-152">Texto de ayuda en las opciones admitidas por los componentes individuales del instalador devuelto por la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d72-152">Help text on the options supported by individual installer components is returned by the <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="15d72-153">Es posible obtener acceso mediante programación a las opciones individuales especificadas en la línea de comandos desde la propiedad <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d72-153">The individual options that have been entered on the command line are accessible programmatically from the <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="15d72-154">Todas las opciones y parámetros de la línea de comandos se escriben en el archivo de registro de la instalación.</span><span class="sxs-lookup"><span data-stu-id="15d72-154">All options and command-line parameters are written to the installation log file.</span></span> <span data-ttu-id="15d72-155">Sin embargo, si utiliza el parámetro `/Password`, que reconocen algunos componentes del instalador, la información de la contraseña se reemplazará por ocho asteriscos (\*) y no aparecerá en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="15d72-155">However, if you use the `/Password` parameter, which is recognized by some installer components, the password information will be replaced by eight asterisks (\*) and will not appear in the log file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15d72-156">En algunos casos, los parámetros pasados al instalador pueden incluir información confidencial o de identificación personal que, de forma predeterminada, se escribe en un archivo de registro de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="15d72-156">In some cases, parameters passed to the installer may include sensitive or personally identifiable information, which, by default, is written to a plain text log file.</span></span> <span data-ttu-id="15d72-157">Para impedir este comportamiento, puede suprimir el archivo de registro; para ello, especifique `/LogFile=` (sin el argumento *filename*) después de Installutil.exe en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="15d72-157">To prevent this behavior, you can suppress the log file by specifying `/LogFile=` (with no *filename* argument) after Installutil.exe on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="15d72-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15d72-158">Remarks</span></span>

<span data-ttu-id="15d72-159">Las aplicaciones de .NET Framework constan de archivos de programa tradicionales y recursos asociados, como colas de mensajes, registros de eventos y contadores de rendimiento que se deben crear al implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15d72-159">.NET Framework applications consist of traditional program files and associated resources, such as message queues, event logs, and performance counters that must be created when the application is deployed.</span></span> <span data-ttu-id="15d72-160">Se pueden utilizar componentes del instalador de un ensamblado para crear estos recursos cuando se instala la aplicación y para quitarlos cuando la aplicación se desinstale.</span><span class="sxs-lookup"><span data-stu-id="15d72-160">You can use an assembly's installer components to create these resources when your application is installed and to remove them when your application is uninstalled.</span></span> <span data-ttu-id="15d72-161">Installutil.exe detecta y ejecuta estos componentes del instalador.</span><span class="sxs-lookup"><span data-stu-id="15d72-161">Installutil.exe detects and executes these installer components.</span></span>

<span data-ttu-id="15d72-162">Se pueden especificar varios ensamblados en la misma línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="15d72-162">You can specify multiple assemblies on the same command line.</span></span> <span data-ttu-id="15d72-163">Las opciones situadas delante de un nombre de ensamblado se aplican a la instalación de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15d72-163">Any option that occurs before an assembly name applies to that assembly's installation.</span></span> <span data-ttu-id="15d72-164">Salvo para `/u` y `/AssemblyName`, las opciones son acumulativas pero reemplazables.</span><span class="sxs-lookup"><span data-stu-id="15d72-164">Except for `/u` and `/AssemblyName`, options are cumulative but overridable.</span></span> <span data-ttu-id="15d72-165">Es decir, las opciones especificadas para un ensamblado se aplican a todos los ensamblados posteriores salvo que la opción se especifique con un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="15d72-165">That is, options specified for one assembly apply to all subsequent assemblies unless the option is specified with a new value.</span></span>

<span data-ttu-id="15d72-166">Si se ejecuta Installutil.exe con un ensamblado sin especificar opciones, la herramienta coloca los tres archivos siguientes en el directorio del ensamblado:</span><span class="sxs-lookup"><span data-stu-id="15d72-166">If you run Installutil.exe against an assembly without specifying any options, it places the following three files into the assembly's directory:</span></span>

- <span data-ttu-id="15d72-167">InstallUtil.InstallLog: contiene una descripción general del progreso de la instalación.</span><span class="sxs-lookup"><span data-stu-id="15d72-167">InstallUtil.InstallLog - Contains a general description of the installation progress.</span></span>

- <span data-ttu-id="15d72-168">*assemblyname*.InstallLog: contiene información específica para la fase de confirmación del proceso de la instalación.</span><span class="sxs-lookup"><span data-stu-id="15d72-168">*assemblyname*.InstallLog - Contains information specific to the commit phase of the installation process.</span></span> <span data-ttu-id="15d72-169">Para obtener más información sobre la fase de confirmación, vea el método <xref:System.Configuration.Install.Installer.Commit%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d72-169">For more information about the commit phase, see the <xref:System.Configuration.Install.Installer.Commit%2A> method.</span></span>

- <span data-ttu-id="15d72-170">*assemblyname*.InstallState: contiene los datos usados para desinstalar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15d72-170">*assemblyname*.InstallState - Contains data used to uninstall the assembly.</span></span>

<span data-ttu-id="15d72-171">Installutil.exe usa la reflexión para inspeccionar los ensamblados especificados y buscar todos los tipos <xref:System.Configuration.Install.Installer> que tengan el atributo <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="15d72-171">Installutil.exe uses reflection to inspect the specified assemblies and to find all <xref:System.Configuration.Install.Installer> types that have the <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> attribute set to `true`.</span></span> <span data-ttu-id="15d72-172">A continuación, la herramienta ejecuta el método <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> o <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> en cada una de las instancias del tipo <xref:System.Configuration.Install.Installer>.</span><span class="sxs-lookup"><span data-stu-id="15d72-172">The tool then executes either the <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> or the <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> method on each instance of the <xref:System.Configuration.Install.Installer> type.</span></span> <span data-ttu-id="15d72-173">Installutil.exe realiza la instalación de forma transaccional; es decir, si se produce un error en la instalación de uno de los ensamblados, se revierten las instalaciones de los demás ensamblados.</span><span class="sxs-lookup"><span data-stu-id="15d72-173">Installutil.exe performs installation in a transactional manner; that is, if one of the assemblies fails to install, it rolls back the installations of all other assemblies.</span></span> <span data-ttu-id="15d72-174">El proceso de desinstalación no es transaccional.</span><span class="sxs-lookup"><span data-stu-id="15d72-174">Uninstall is not transactional.</span></span>

<span data-ttu-id="15d72-175">Installutil.exe no puede instalar ni desinstalar los ensamblados con firma retrasada, pero puede instalar o desinstalar los ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="15d72-175">Installutil.exe cannot install or uninstall delay-signed assemblies, but it can install or uninstall strong-named assemblies.</span></span>

<span data-ttu-id="15d72-176">A partir de la versión 2.0 de .NET Framework, la versión de 32 bits de Common Language Runtime (CLR) se distribuye solo con la versión de 32 bits de la herramienta de instalación, aunque la versión de 64 bits de CLR se distribuye tanto con la versión de 32 bits como con la versión de 64 bits de dicha herramienta.</span><span class="sxs-lookup"><span data-stu-id="15d72-176">Starting with the .NET Framework version 2.0, the 32-bit version of the common language runtime (CLR) ships with only the 32-bit version of the Installer tool, but the 64-bit version of the CLR ships with both 32-bit and 64-bit versions of the Installer tool.</span></span> <span data-ttu-id="15d72-177">Cuando utilice el CLR de 64 bits, emplee la herramienta de instalación de 32 bits para instalar los ensamblados de 32 bits y la herramienta de instalación de 64 bits para instalar los ensamblados de 64 bits y del Lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="15d72-177">When using the 64-bit CLR, use the 32-bit Installer tool to install 32-bit assemblies, and the 64-bit Installer tool to install 64-bit and Microsoft intermediate language (MSIL) assemblies.</span></span> <span data-ttu-id="15d72-178">Ambas versiones de la herramienta de instalación se comportan de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="15d72-178">Both versions of the Installer tool behave the same.</span></span>

<span data-ttu-id="15d72-179">No se puede utilizar Installutil.exe para implementar un servicio de Windows creado mediante C++, ya que Installutil.exe no reconoce el código nativo incrustado generado por el compilador de C++.</span><span class="sxs-lookup"><span data-stu-id="15d72-179">You cannot use Installutil.exe to deploy a Windows service that was created by using C++, because Installutil.exe cannot recognize the embedded native code that is produced by the C++ compiler.</span></span> <span data-ttu-id="15d72-180">Si intenta implementar un servicio de Windows de C++ con Installutil.exe, se producirá una excepción como <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="15d72-180">If you try to deploy a C++ Windows service with Installutil.exe, an exception such as <xref:System.BadImageFormatException> will be thrown.</span></span> <span data-ttu-id="15d72-181">Para trabajar con este escenario, mueva el código de servicio a un módulo de C++ y, a continuación, escriba el objeto del instalador en C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15d72-181">To work with this scenario, move the service code to a C++ module, and then write the installer object in C# or Visual Basic.</span></span>

## <a name="examples"></a><span data-ttu-id="15d72-182">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15d72-182">Examples</span></span>

<span data-ttu-id="15d72-183">El comando siguiente muestra una descripción de la sintaxis y las opciones de comando para InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="15d72-183">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span>

```console
installutil /?
```

<span data-ttu-id="15d72-184">El comando siguiente muestra una descripción de la sintaxis y las opciones de comando para InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="15d72-184">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="15d72-185">También muestra una descripción y la lista de opciones admitidas por los componentes del instalador en `myAssembly.exe` si el texto de ayuda se ha asignado a la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> del instalador.</span><span class="sxs-lookup"><span data-stu-id="15d72-185">It also displays a description and list of options supported by the installer components in `myAssembly.exe` if help text has been assigned to the installer's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span>

```console
installutil /? myAssembly.exe
```

<span data-ttu-id="15d72-186">El comando siguiente ejecuta los componentes del instalador en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="15d72-186">The following command executes the installer components in the assembly `myAssembly.exe`.</span></span>

```console
installutil myAssembly.exe
```

<span data-ttu-id="15d72-187">El siguiente comando ejecuta los componentes del instalador en un ensamblado mediante el modificador `/AssemblyName` y un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="15d72-187">The following command executes the installer components in an assembly by using the `/AssemblyName` switch and a fully qualified name.</span></span>

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="15d72-188">El comando siguiente ejecuta los componentes del instalador en un ensamblado especificado por nombre de archivo y en un ensamblado especificado por nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="15d72-188">The following command executes the installer components in an assembly specified by file name and in an assembly specified by strong name.</span></span> <span data-ttu-id="15d72-189">Tenga en cuenta que todos los ensamblados especificados por nombre de archivo deben preceder a los especificados por nombre seguro en la línea de comandos, ya que la opción `/AssemblyName` no se puede invalidar.</span><span class="sxs-lookup"><span data-stu-id="15d72-189">Note that all assemblies specified by file name must precede assemblies specified by strong name on the command line, because the `/AssemblyName` option cannot be overridden.</span></span>

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="15d72-190">El comando siguiente ejecuta los componentes del desinstalador en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="15d72-190">The following command executes the uninstaller components in the assembly `myAssembly.exe`.</span></span>

```console
installutil /u myAssembly.exe
```

<span data-ttu-id="15d72-191">El comando siguiente ejecuta los componentes del desinstalador en los ensamblados `myAssembly1.exe` y `myAssembly2.exe`.</span><span class="sxs-lookup"><span data-stu-id="15d72-191">The following command executes the uninstaller components in the assemblies `myAssembly1.exe` and `myAssembly2.exe`.</span></span>

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

<span data-ttu-id="15d72-192">Dado que la posición de la opción `/u` en la línea de comandos no es importante, esta es equivalente al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="15d72-192">Because the position of the `/u` option on the command line is not important, this is equivalent to the following command.</span></span>

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

<span data-ttu-id="15d72-193">El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe` y especifica la información del progreso que se escribirá en `myLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="15d72-193">The following command executes the installers in the assembly `myAssembly.exe` and specifies that progress information will be written to `myLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

<span data-ttu-id="15d72-194">El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe`, especifica que la información de progreso debe escribirse en `myLog.InstallLog` y usa la opción `/reg` personalizada de los instaladores para especificar las actualizaciones que se deben realizar en el Registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="15d72-194">The following command executes the installers in the assembly `myAssembly.exe`, specifies that progress information should be written to `myLog.InstallLog`, and uses the installers' custom `/reg` option to specify that updates should be made to the system registry.</span></span>

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

<span data-ttu-id="15d72-195">El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe`, usa la opción `/email` personalizada del instalador para especificar la dirección de correo electrónico del usuario e impide que los resultados se envíen al archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="15d72-195">The following command executes the installers in the assembly `myAssembly.exe`, uses the installer's custom `/email` option to specify the user's email address, and suppresses output to the log file.</span></span>

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

<span data-ttu-id="15d72-196">El comando siguiente escribe el progreso de instalación de `myAssembly.exe` en `myLog.InstallLog` y el progreso de `myTestAssembly.exe` en `myTestLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="15d72-196">The following command writes the installation progress for `myAssembly.exe` to `myLog.InstallLog` and writes the progress for `myTestAssembly.exe` to `myTestLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a><span data-ttu-id="15d72-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="15d72-197">See also</span></span>

- <xref:System.Configuration.Install>
- [<span data-ttu-id="15d72-198">Herramientas</span><span class="sxs-lookup"><span data-stu-id="15d72-198">Tools</span></span>](index.md)
- [<span data-ttu-id="15d72-199">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="15d72-199">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
