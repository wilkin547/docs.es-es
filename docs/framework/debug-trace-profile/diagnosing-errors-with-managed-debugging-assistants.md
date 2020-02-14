---
title: Diagnóstico de errores con asistentes para la depuración administrada
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216555"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Diagnóstico de errores con asistentes para la depuración administrada

Los asistentes de depuración administrada (MDA) son ayudas para la depuración que funcionan en conjunción con Common Language Runtime (CLR) para proporcionar información sobre estado en tiempo de ejecución. Los asistentes generan mensajes informativos sobre eventos en tiempo de ejecución que de otra forma no pueden interceptar. Puede utilizar MDA para aislar errores de la aplicación difíciles de encontrar que aparecen al realizar la transición entre código administrado y no administrado.

Puede [habilitar o deshabilitar](#enable-and-disable-mdas) todos los MDA agregando una clave al registro de Windows o estableciendo una variable de entorno. Puede habilitar MDA específicos mediante los valores de configuración de la aplicación. Puede establecer opciones de configuración adicionales para algunos MDA concretos en el archivo de configuración de la aplicación. Dado que estos archivos de configuración se analizan cuando se carga el motor en tiempo de ejecución, debe habilitar el MDA antes de que se inicie la aplicación administrada. No puede habilitarlo para aplicaciones que ya se han iniciado.

En la tabla siguiente se enumeran los MDA que se incluyen con el .NET Framework:

|||
|-|-|
|[asynchronousThreadAbort](asynchronousthreadabort-mda.md)|[bindingFailure](bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](dirtycastandcalloninterface-mda.md)|[disconnectedContext](disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](failedqi-mda.md)|[fatalExecutionEngineError](fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](invalidapartmentstatechange-mda.md)|
|[invalidCERCall](invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](invalidgchandlecookie-mda.md)|[invalidIUnknown](invalidiunknown-mda.md)|
|[invalidMemberDeclaration](invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](invalidvariant-mda.md)|[jitCompilationStart](jitcompilationstart-mda.md)|
|[loaderLock](loaderlock-mda.md)|[loadFromContext](loadfromcontext-mda.md)|
|[marshalCleanupError](marshalcleanuperror-mda.md)|[marshaling](marshaling-mda.md)|
|[memberInfoCacheCreation](memberinfocachecreation-mda.md)|[moduloObjectHashcode](moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](noncomvisiblebaseclass-mda.md)|[notMarshalable](notmarshalable-mda.md)|
|[openGenericCERCall](opengenericcercall-mda.md)|[overlappedFreeError](overlappedfreeerror-mda.md)|
|[pInvokeLog](pinvokelog-mda.md)|[pInvokeStackImbalance](pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](raceonrcwcleanup-mda.md)|[reentrancy](reentrancy-mda.md)|
|[releaseHandleFailed](releasehandlefailed-mda.md)|[reportAvOnComRelease](reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](streamwriterbuffereddatalost-mda.md)|[virtualCERCall](virtualcercall-mda.md)|

De forma predeterminada, .NET Framework activa un subconjunto de MDA para todos los depuradores administrados. Para ver el conjunto predeterminado en Visual Studio, elija **configuración de excepciones** de **Windows** > en el menú **depurar** y, a continuación, expanda la lista **asistentes para la depuración administrada** .

![Ventana Configuración de excepciones en Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Habilitar y deshabilitar MDA

Puede habilitar y deshabilitar los MDA mediante una clave del Registro, una variable de entorno o valores de configuración de la aplicación. La clave del Registro o la variable de entorno tienen que estar habilitadas para utilizar los valores de configuración de la aplicación.

> [!TIP]
> En lugar de deshabilitar los MDA, puede impedir que Visual Studio muestre el cuadro de diálogo MDA cada vez que se reciba una notificación de MDA. Para ello, elija **configuración de excepciones** de **Windows** > en el menú **depurar** , expanda la lista asistentes para la **depuración administrada** y, a continuación, Active o desactive la casilla **interrumpir cuando se produzca** la activación del MDA individual.

### <a name="registry-key"></a>Clave del Registro

Para habilitar los MDA, agregue el **HKEY_LOCAL_MACHINE \software\microsoft\\.** Subclave NETFramework\MDA (de tipo REG_SZ, valor 1) en el registro de Windows. Copie el ejemplo siguiente en un archivo de texto denominado *MDAEnable. reg*. Abra el editor del registro de Windows (regedit. exe) y, en el menú **archivo** , elija **importar**. Seleccione el archivo *MDAEnable. reg* para habilitar los MDA en ese equipo. Si se establece la subclave en **un** valor de cadena de 1 (no el valor DWORD de **1**), se habilita la lectura de la configuración de MDA del archivo *applicationName. Suffix*. MDA. config. Por ejemplo, el archivo de configuración de MDA para el Bloc de notas se denominará Notepad. exe. MDA. config.

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

Si el equipo ejecuta una aplicación de 32 bits en un sistema operativo de 64 bits, la clave de MDA debe establecerse de la forma siguiente:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

Consulte [valores de configuración específicos de la aplicación](#application-specific-configuration-settings) para obtener más información. La variable de entorno COMPLUS_MDA puede invalidar la configuración del Registro. Consulte [variable de entorno](#environment-variable) para obtener más información.

Para deshabilitar los MDA, establezca la subclave MDA en **0** (cero) mediante el editor del registro de Windows.

De forma predeterminada, algunos MDA están habilitados cuando se ejecuta una aplicación asociada a un depurador, incluso sin agregar la clave del Registro. Puede deshabilitar estos asistentes ejecutando el archivo *MDADisable. reg* como se describió anteriormente en esta sección.

### <a name="environment-variable"></a>Variable de entorno

La activación de MDA también puede controlarse mediante la variable de entorno COMPLUS_MDA, que reemplaza la clave del Registro. La cadena COMPLUS_MDA es una lista delimitada por puntos y comas de nombres de MDA u otras cadenas de control especiales, y no distingue entre mayúsculas y minúsculas. Al iniciar bajo un depurador administrado o no administrado se habilita de forma predeterminada un conjunto de MDA. Esto se realiza anteponiendo implícitamente al valor de la variable de entorno o de la clave del Registro la lista delimitada por puntos y comas de los MDA habilitados de manera predeterminada bajo depuradores. Las cadenas de control especiales son las siguientes:

- `0` - Desactiva todos los MDA.

- `1`: lee la configuración de MDA de *NombreAplicación*.mda.config.

- `managedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable administrado bajo un depurador.

- `unmanagedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable no administrado bajo un depurador.

Si hay ajustes contradictorios, los más recientes reemplazan los ajustes anteriores:

- `COMPLUS_MDA=0` deshabilita todos los MDA, incluidos los habilitados implícitamente bajo un depurador.

- `COMPLUS_MDA=gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` además de los MDA habilitados implícitamente bajo un depurador.

- `COMPLUS_MDA=0;gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` pero deshabilita los MDA que, de otro modo, estarían habilitados implícitamente bajo un depurador.

### <a name="application-specific-configuration-settings"></a>Opciones de configuración específicas de la aplicación

Puede habilitar, deshabilitar y configurar individualmente algunos asistentes en el archivo de configuración de MDA para la aplicación. Para habilitar el uso de un archivo de configuración de la aplicación para configurar los MDA, es necesario establecer la clave del Registro MDA o la variable de entorno COMPLUS_MDA. El archivo de configuración de la aplicación se encuentra normalmente en el mismo directorio que el archivo ejecutable (.exe) de la aplicación. El nombre de archivo toma el formato *applicationName*. MDA. config; por ejemplo, Notepad. exe. MDA. config. Los asistentes que están habilitados en el archivo de configuración de la aplicación pueden tener atributos o elementos específicamente diseñados para controlar el comportamiento del asistente.

En el ejemplo siguiente se muestra cómo habilitar y configurar el [cálculo de referencias](marshaling-mda.md):

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

El MDA de `Marshaling` emite información sobre el tipo administrado cuyas referencias se calculan a un tipo no administrado para cada transición de administrado a no administrado en la aplicación. El MDA de `Marshaling` también puede filtrar los nombres de los campos de método y estructura proporcionados en los elementos secundarios **methodFilter** y **fieldFilter** , respectivamente.

En el ejemplo siguiente se muestra cómo habilitar varios MDA mediante su configuración predeterminada:

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> Cuando se especifica más de un asistente en un archivo de configuración, se deben enumerar en orden alfabético. Por ejemplo, si se desea habilitar los MDA `virtualCERCall` e `invalidCERCall`, se debe agregar la entrada `<invalidCERCall />` antes que la entrada `<virtualCERCall />`. Si las entradas no están en orden alfabético, se muestra un mensaje de excepción no controlada de archivo de configuración no válido.

## <a name="mda-exceptions"></a>Excepciones de MDA

Cuando se habilita un MDA, está activo incluso cuando el código no se está ejecutando en un depurador. Si se genera un evento MDA cuando un depurador no está presente, el mensaje del evento se presenta en un cuadro de diálogo de excepción no controlada, aunque no se trata de una excepción no controlada. Para evitar el cuadro de diálogo, quite las opciones que habilitan MDA cuando el código no se está ejecutando en un entorno de depuración.

Cuando el código se ejecuta en el entorno de desarrollo integrado (IDE) de Visual Studio, puede evitar el cuadro de diálogo de excepción que aparece para determinados eventos de MDA. Para ello, en el menú **depurar** , elija **configuración de excepciones**de > de **Windows** . En la ventana **configuración de excepciones** , expanda la lista asistentes para la **depuración administrada** y, a continuación, desactive la casilla **interrumpir cuando se produzca** el MDA individual. También puede utilizar este cuadro de diálogo para *Habilitar* la presentación de los cuadros de diálogo de excepción de MDA.

## <a name="mda-output"></a>Salida del MDA

La salida del MDA es similar al ejemplo siguiente, que muestra la salida del MDA `PInvokeStackImbalance`:

**Una llamada a la función PInvoke ' MDATest! MDATest. Program:: StdCall ' ha desequilibrado la pila. Probablemente, esto se debe a que la firma de PInvoke administrada no coincide con la firma de destino no administrada. Compruebe que la Convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**

## <a name="see-also"></a>Consulte también

- [Depurar, trazar y generar perfiles](index.md)
