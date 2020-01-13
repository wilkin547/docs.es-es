---
title: 'Cómo: Depuración de problemas de activación de CLR'
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 602ee3c88237a902d48339836fbe25f636ae9705
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716504"
---
# <a name="how-to-debug-clr-activation-issues"></a><span data-ttu-id="a1846-102">Cómo: Depuración de problemas de activación de CLR</span><span class="sxs-lookup"><span data-stu-id="a1846-102">How to debug CLR activation issues</span></span>

<span data-ttu-id="a1846-103">Si detecta problemas al intentar que la aplicación se ejecute con la versión correcta de Common Language Runtime (CLR), puede ver y depurar los registros de activación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-103">If you encounter problems in getting your application to run with the correct version of the common language runtime (CLR), you can view and debug CLR activation logs.</span></span> <span data-ttu-id="a1846-104">Estos registros pueden resultar muy útiles a la hora de determinar la causa de un problema de activación, cuando la aplicación carga una versión de CLR que no es la prevista o simplemente no lo carga.</span><span class="sxs-lookup"><span data-stu-id="a1846-104">These logs can be very useful in determining the root cause of an activation issue, when your application either loads a different CLR version than expected or doesn't load the CLR at all.</span></span> <span data-ttu-id="a1846-105">En [Errores de inicialización de .NET Framework: Administración de la experiencia del usuario](initialization-errors-managing-the-user-experience.md) se habla de la experiencia de no encontrar ningún CLR para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1846-105">The [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) discusses the experience when no CLR is found for an application.</span></span>

<span data-ttu-id="a1846-106">El registro de activación de CLR se puede habilitar en todo el sistema mediante una clave del Registro HKEY_LOCAL_MACHINE o una variable de entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1846-106">CLR activation logging can be enabled system-wide by using an HKEY_LOCAL_MACHINE registry key or a system environment variable.</span></span> <span data-ttu-id="a1846-107">Se generará el registro hasta que se quite la entrada del Registro o la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="a1846-107">The log will be generated until the registry entry or the environment variable is removed.</span></span> <span data-ttu-id="a1846-108">También puede emplear una variable de entorno de proceso local o de usuario para habilitar el registro con un ámbito y una duración diferentes.</span><span class="sxs-lookup"><span data-stu-id="a1846-108">Alternatively, you can use a user or process-local environment variable to enable logging with a different scope and duration.</span></span>

<span data-ttu-id="a1846-109">Los registros de activación de CLR no se deben confundir con los [registros de enlaces de ensamblados](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), que son completamente diferentes.</span><span class="sxs-lookup"><span data-stu-id="a1846-109">CLR activation logs shouldn't be confused with [assembly binding logs](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), which are entirely different.</span></span>

## <a name="to-enable-clr-activation-logging"></a><span data-ttu-id="a1846-110">Para habilitar el registro de activación de CLR</span><span class="sxs-lookup"><span data-stu-id="a1846-110">To enable CLR activation logging</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="a1846-111">Con el Registro</span><span class="sxs-lookup"><span data-stu-id="a1846-111">Using the registry</span></span>

1. <span data-ttu-id="a1846-112">En el Editor del Registro, vaya a la carpeta HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework (en un equipo de 32 bits) o HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (en un equipo de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="a1846-112">In the Registry Editor, navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (on a 32-bit computer) or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework folder (on a 64-bit computer).</span></span>

2. <span data-ttu-id="a1846-113">Agregue un valor de cadena denominado `CLRLoadLogDir` y establézcalo en la ruta de acceso completa de un directorio existente donde quiera almacenar los registros de activación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-113">Add a string value named `CLRLoadLogDir`, and set it to the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

<span data-ttu-id="a1846-114">El registro de activación permanece habilitado hasta que se quita el valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="a1846-114">Activation logging remains enabled until you remove the string value.</span></span>

### <a name="using-an-environment-variable"></a><span data-ttu-id="a1846-115">Con una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="a1846-115">Using an environment variable</span></span>

- <span data-ttu-id="a1846-116">Establezca la variable de entorno `COMPLUS_CLRLoadLogDir` en una cadena que represente la ruta de acceso completa de un directorio existente donde quiera almacenar los registros de activación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-116">Set the `COMPLUS_CLRLoadLogDir` environment variable to a string that represents the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

    <span data-ttu-id="a1846-117">La manera en que establezca la variable de entorno determina su ámbito:</span><span class="sxs-lookup"><span data-stu-id="a1846-117">How you set the environment variable determines its scope:</span></span>

  - <span data-ttu-id="a1846-118">Si se establece en el nivel de sistema, el registro de activación está habilitado para todas las aplicaciones de .NET Framework del equipo hasta que se quita la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="a1846-118">If you set it at the system level, activation logging is enabled for all .NET Framework applications on that computer until the environment variable is removed.</span></span>

  - <span data-ttu-id="a1846-119">Si se establece en el nivel de usuario, el registro de activación está habilitado solo para la cuenta de usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a1846-119">If you set it at the user level, activation logging is enabled only for the current user account.</span></span> <span data-ttu-id="a1846-120">El registro continúa hasta que se quita la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="a1846-120">Logging continues until the environment variable is removed.</span></span>

  - <span data-ttu-id="a1846-121">Si se establece desde dentro del proceso antes de cargar el CLR, el registro de activación está habilitado hasta que finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="a1846-121">If you set it from within the process before loading the CLR, activation logging is enabled until the process terminates.</span></span>

  - <span data-ttu-id="a1846-122">Si se establece en un símbolo del sistema antes de ejecutar una aplicación, el registro de activación está habilitado para cualquier aplicación que se ejecute desde ese símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1846-122">If you set it at a command prompt before you run an application, activation logging is enabled for any application that is run from that command prompt.</span></span>

    <span data-ttu-id="a1846-123">Por ejemplo, para almacenar los registros de activación en el directorio c:\clrloadlogs con ámbito de nivel de proceso, abra una ventana del símbolo del sistema y escriba lo siguiente antes de ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a1846-123">For example, to store activation logs in the c:\clrloadlogs directory with process-level scope, open a Command Prompt window and type the following before you run the application:</span></span>

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a><span data-ttu-id="a1846-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1846-124">Example</span></span>

<span data-ttu-id="a1846-125">Los registros de activación de CLR proporcionan una gran cantidad de datos sobre la activación de CLR y el uso de las API de hospedaje de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-125">CLR activation logs provide a large amount of data about CLR activation and the use of the CLR hosting APIs.</span></span> <span data-ttu-id="a1846-126">La mayoría de estos datos son usados internamente por Microsoft, pero algunos también pueden resultar útiles para los desarrolladores, como se explica en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a1846-126">Most of this data is used internally by Microsoft, but some of the data can also be useful to developers, as described in this article.</span></span>

<span data-ttu-id="a1846-127">El registro refleja el orden en que se ha llamado a las API de hospedaje de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-127">The log reflects the order in which the CLR hosting APIs were called.</span></span> <span data-ttu-id="a1846-128">También incluye datos útiles sobre el conjunto de runtimes instalados detectados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a1846-128">It also includes useful data about the set of installed runtimes detected on the computer.</span></span> <span data-ttu-id="a1846-129">El formato del registro de activación de CLR no está documentado, pero se puede usar para ayudar a los desarrolladores que necesitan solucionar problemas de activación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a1846-129">The CLR activation log format is not itself documented, but can be used to aid developers who need to resolve CLR activation issues.</span></span>

> [!NOTE]
> <span data-ttu-id="a1846-130">No se puede abrir un registro de activación hasta que el proceso que usa el CLR ha concluido.</span><span class="sxs-lookup"><span data-stu-id="a1846-130">You cannot open an activation log until the process that uses the CLR has terminated.</span></span>

> [!NOTE]
> <span data-ttu-id="a1846-131">Los registros de activación de CLR no están localizados; siempre se generan en inglés.</span><span class="sxs-lookup"><span data-stu-id="a1846-131">CLR activation logs are not localized; they are always generated in the English language.</span></span>

<span data-ttu-id="a1846-132">En el siguiente ejemplo de un registro de activación, la información más útil está resaltada y se explica tras el registro.</span><span class="sxs-lookup"><span data-stu-id="a1846-132">In the following example of an activation log, the most useful information is highlighted and described after the log.</span></span>

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- <span data-ttu-id="a1846-133">**Registro de carga CLR** proporciona la ruta de acceso al ejecutable que ha iniciado el proceso de carga del código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1846-133">**CLR Loading log** provides the path to the executable that started the process that loaded managed code.</span></span> <span data-ttu-id="a1846-134">Tenga en cuenta que podría ser un host nativo.</span><span class="sxs-lookup"><span data-stu-id="a1846-134">Note that this could be a native host.</span></span>

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- <span data-ttu-id="a1846-135">**Runtime instalado** es el conjunto de versiones de CLR instaladas en el equipo que son aptas para la solicitud de activación.</span><span class="sxs-lookup"><span data-stu-id="a1846-135">**Installed Runtime** is the set of CLR versions installed on the computer that are candidates for the activation request.</span></span>

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- <span data-ttu-id="a1846-136">**se generó con la versión** es la versión de CLR que se ha usado para crear el binario que se ha proporcionado a un método como [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1846-136">**built with version** is the version of the CLR that was used to build the binary that was provided to a method such as [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span></span>

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- <span data-ttu-id="a1846-137">**instalación de características previa petición** hace referencia a la habilitación de .NET Framework 3.5 en Windows 8.</span><span class="sxs-lookup"><span data-stu-id="a1846-137">**feature-on-demand installation** refers to enabling the .NET Framework 3.5 on Windows 8.</span></span> <span data-ttu-id="a1846-138">Vea [Errores de inicialización de .NET Framework: Administración de la experiencia del usuario](initialization-errors-managing-the-user-experience.md) para obtener más información sobre este escenario.</span><span class="sxs-lookup"><span data-stu-id="a1846-138">See [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) for more information about this scenario.</span></span>

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a><span data-ttu-id="a1846-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1846-139">See also</span></span>

- [<span data-ttu-id="a1846-140">Implementación</span><span class="sxs-lookup"><span data-stu-id="a1846-140">Deployment</span></span>](index.md)
- [<span data-ttu-id="a1846-141">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a1846-141">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
