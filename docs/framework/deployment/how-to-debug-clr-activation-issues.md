---
title: 'Cómo: Depuración de problemas de activación de CLR'
description: Vea cómo depurar problemas de activación de Common Language Runtime (CLR) en .NET. Consulte y depure los registros de activación de CLR, que pueden ser útiles a la hora de determinar las causas principales.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 5215e82aebf93fa8d6d1937563ab348126a01d97
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622619"
---
# <a name="how-to-debug-clr-activation-issues"></a>Cómo: Depuración de problemas de activación de CLR

Si detecta problemas al intentar que la aplicación se ejecute con la versión correcta de Common Language Runtime (CLR), puede ver y depurar los registros de activación de CLR. Estos registros pueden resultar muy útiles a la hora de determinar la causa de un problema de activación, cuando la aplicación carga una versión de CLR que no es la prevista o simplemente no lo carga. En [Errores de inicialización de .NET Framework: Administración de la experiencia del usuario](initialization-errors-managing-the-user-experience.md) se habla de la experiencia de no encontrar ningún CLR para una aplicación.

El registro de activación de CLR se puede habilitar en todo el sistema mediante una clave del Registro HKEY_LOCAL_MACHINE o una variable de entorno del sistema. Se generará el registro hasta que se quite la entrada del Registro o la variable de entorno. También puede emplear una variable de entorno de proceso local o de usuario para habilitar el registro con un ámbito y una duración diferentes.

Los registros de activación de CLR no se deben confundir con los [registros de enlaces de ensamblados](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), que son completamente diferentes.

## <a name="to-enable-clr-activation-logging"></a>Para habilitar el registro de activación de CLR

### <a name="using-the-registry"></a>Con el Registro

1. En el Editor del Registro, vaya a la carpeta HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework (en un equipo de 32 bits) o HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (en un equipo de 64 bits).

2. Agregue un valor de cadena denominado `CLRLoadLogDir` y establézcalo en la ruta de acceso completa de un directorio existente donde quiera almacenar los registros de activación de CLR.

El registro de activación permanece habilitado hasta que se quita el valor de cadena.

### <a name="using-an-environment-variable"></a>Con una variable de entorno

- Establezca la variable de entorno `COMPLUS_CLRLoadLogDir` en una cadena que represente la ruta de acceso completa de un directorio existente donde quiera almacenar los registros de activación de CLR.

    La manera en que establezca la variable de entorno determina su ámbito:

  - Si se establece en el nivel de sistema, el registro de activación está habilitado para todas las aplicaciones de .NET Framework del equipo hasta que se quita la variable de entorno.

  - Si se establece en el nivel de usuario, el registro de activación está habilitado solo para la cuenta de usuario actual. El registro continúa hasta que se quita la variable de entorno.

  - Si se establece desde dentro del proceso antes de cargar el CLR, el registro de activación está habilitado hasta que finaliza el proceso.

  - Si se establece en un símbolo del sistema antes de ejecutar una aplicación, el registro de activación está habilitado para cualquier aplicación que se ejecute desde ese símbolo del sistema.

    Por ejemplo, para almacenar los registros de activación en el directorio c:\clrloadlogs con ámbito de nivel de proceso, abra una ventana del símbolo del sistema y escriba lo siguiente antes de ejecutar la aplicación:

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a>Ejemplo

Los registros de activación de CLR proporcionan una gran cantidad de datos sobre la activación de CLR y el uso de las API de hospedaje de CLR. La mayoría de estos datos son usados internamente por Microsoft, pero algunos también pueden resultar útiles para los desarrolladores, como se explica en este artículo.

El registro refleja el orden en que se ha llamado a las API de hospedaje de CLR. También incluye datos útiles sobre el conjunto de runtimes instalados detectados en el equipo. El formato del registro de activación de CLR no está documentado, pero se puede usar para ayudar a los desarrolladores que necesitan solucionar problemas de activación de CLR.

> [!NOTE]
> No se puede abrir un registro de activación hasta que el proceso que usa el CLR ha concluido.

> [!NOTE]
> Los registros de activación de CLR no están localizados; siempre se generan en inglés.

En el siguiente ejemplo de un registro de activación, la información más útil está resaltada y se explica tras el registro.

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

- **Registro de carga CLR** proporciona la ruta de acceso al ejecutable que ha iniciado el proceso de carga del código administrado. Tenga en cuenta que podría ser un host nativo.

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- **Runtime instalado** es el conjunto de versiones de CLR instaladas en el equipo que son aptas para la solicitud de activación.

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- **se generó con la versión** es la versión de CLR que se ha usado para crear el binario que se ha proporcionado a un método como [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- **instalación de características previa petición** hace referencia a la habilitación de .NET Framework 3.5 en Windows 8. Vea [Errores de inicialización de .NET Framework: Administración de la experiencia del usuario](initialization-errors-managing-the-user-experience.md) para obtener más información sobre este escenario.

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a>Vea también

- [Implementación](index.md)
- [Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
