---
title: "Diagnóstico de errores con asistentes de depuraciones administradas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EHMDA
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
caps.latest.revision: "63"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12a96068412f05d48b8b006385c66f3efbbf9870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="diagnosing-errors-with-managed-debugging-assistants"></a>Diagnóstico de errores con asistentes de depuraciones administradas
Los asistentes de depuración administrada (MDA) son ayudas para la depuración que funcionan en conjunción con Common Language Runtime (CLR) para proporcionar información sobre estado en tiempo de ejecución. Los asistentes generan mensajes informativos sobre eventos en tiempo de ejecución que de otra forma no pueden interceptar. Puede utilizar MDA para aislar errores de la aplicación difíciles de encontrar que aparecen al realizar la transición entre código administrado y no administrado. Puede habilitar o deshabilitar todos los MDA si agrega una clave al Registro de Windows o establece una variable de entorno. Puede habilitar MDA específicos mediante los valores de configuración de la aplicación. Puede establecer opciones de configuración adicionales para algunos MDA concretos en el archivo de configuración de la aplicación. Dado que estos archivos de configuración se analizan cuando se carga el motor en tiempo de ejecución, debe habilitar el MDA antes de que se inicie la aplicación administrada. No puede habilitarlo para aplicaciones que ya se han iniciado.  
  
> [!NOTE]
>  Cuando se habilita un asistente para la depuración administrada (MDA), está activo aunque el código no se esté ejecutando en un depurador. Si se genera un evento MDA cuando un depurador no está presente, el mensaje del evento se presenta en un cuadro de diálogo de excepción no controlada, aunque no se trata de una excepción no controlada. Para evitar el cuadro de diálogo, quite las opciones que habilitan MDA cuando el código no se está ejecutando en un entorno de depuración.  
  
> [!NOTE]
>  Cuando el código se ejecuta en el entorno de desarrollo integrado (IDE) de Visual Studio, puede evitar el cuadro de diálogo de excepciones que aparece con determinados eventos de MDA. Para ello, en el menú **Depurar**, haga clic en **Excepciones**. (Si el menú **Depurar** no contiene el comando **Excepciones**, haga clic en **Personalizar** en el menú **Herramientas** para agregarlo). En el cuadro de diálogo **Excepciones**, expanda la lista **Asistentes para la depuración administrada** y, después, desactive la casilla **Producida** de cada MDA. Por ejemplo, para evitar el cuadro de diálogo de excepciones de [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md), desactive la casilla **Producida** situada junto a su nombre en la lista **Asistentes para la depuración administrada**. También puede usar este cuadro de diálogo para habilitar la presentación de los cuadros de diálogo de excepciones de MDA.  
  
 La tabla siguiente muestra los MDA incluidos con .NET Framework.  
  
|||  
|-|-|  
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|  
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|  
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|  
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|  
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|  
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|  
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|  
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|  
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|  
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|  
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|  
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|  
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|  
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|  
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|  
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|  
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|  
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|  
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|  
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|  
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|  
  
 De forma predeterminada, .NET Framework activa un subconjunto de MDA para todos los depuradores administrados. Para ver el valor predeterminado en Visual Studio, haga clic en **Excepciones** en el menú **Depurar**, y expanda la lista **Asistentes para la depuración administrada**.  
  
## <a name="enabling-and-disabling-mdas"></a>Habilitar y deshabilitar MDA  
 Puede habilitar y deshabilitar los MDA mediante una clave del Registro, una variable de entorno o valores de configuración de la aplicación. La clave del Registro o la variable de entorno tienen que estar habilitadas para utilizar los valores de configuración de la aplicación.  
  
 En Visual Studio 2005 y versiones posteriores, cuando se habilita el proceso de hospedaje, no se pueden deshabilitar los MDA que están en el conjunto predeterminado ni habilitar los MDA que no están en el conjunto predeterminado. De forma predeterminada, el proceso de hospedaje está habilitado, por lo que debe deshabilitarse explícitamente.  
  
 Para deshabilitar el proceso de hospedaje en Visual Studio, haga lo siguiente:  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto.  
  
2.  En el menú **Proyecto**, haga clic en **Propiedades**.  
  
     Aparece la ventana **Diseñador de proyectos**.  
  
3.  Haga clic en la pestaña **Depurar**.  
  
4.  En la sección **Habilitar depuradores**, desactive la casilla **Habilitar el proceso de hospedaje de Visual Studio**.  
  
 Sin embargo, deshabilitar el proceso de hospedaje puede afectar al rendimiento. Para que no sea necesario deshabilitar los MDA, no permita que Visual Studio muestre el cuadro de diálogo MDA cuando se reciba una notificación de MDA. Para ello, haga clic en **Excepciones** en el menú **Depurar**, expanda la lista **Asistentes para la depuración administrada** y, después, active o desactive la casilla **Producida** del MDA individual.  
  
### <a name="enabling-and-disabling-mdas-by-using-a-registry-key"></a>Habilitar y deshabilitar MDA utilizando una clave del Registro  
 Puede habilitar MDA agregando la subclave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA (tipo REG_SZ, valor 1) al Registro de Windows. Copie el ejemplo siguiente en un archivo de texto denominado MDAEnable.reg. Abra el Editor del Registro de Windows (RegEdit.exe) y desde el menú **Archivo** elija **Importar**. Seleccione el archivo MDAEnable.reg para habilitar los MDA en ese equipo. Si se establece la subclave en un valor de cadena de 1 (no en un valor DWORD de 1), se habilita la lectura de la configuración de MDA del archivo *NombreAplicación.sufijo*.mda.config. (Por ejemplo, el archivo de configuración de MDA para el Bloc de notas [notepad] se llamaría notepad.exe.mda.config).  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 Si el equipo ejecuta una aplicación de 32 bits en un sistema operativo de 64 bits, la clave de MDA debe establecerse de la forma siguiente:  
  
```  
      Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 Para obtener más información, vea [Habilitar y deshabilitar MDA usando valores de configuración específicos de la aplicación](#appConfig). La variable de entorno COMPLUS_MDA puede invalidar la configuración del Registro. Vea [Habilitar y deshabilitar MDA usando una variable de entorno](#envVariable) para obtener más información.  
  
 Para deshabilitar MDA, establezca la subclave MDA en 0 (cero) utilizando el Editor del Registro de Windows.  
  
 De forma predeterminada, algunos MDA están habilitados cuando se ejecuta una aplicación asociada a un depurador, incluso sin agregar la clave del Registro. Ejemplos de estos asistentes son [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) e [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md). Puede deshabilitar estos asistentes ejecutando el archivo MDADisable.reg como se explica anteriormente en esta sección.  
  
<a name="envVariable"></a>   
### <a name="enabling-and-disabling-mdas-by-using-an-environment-variable"></a>Habilitar y deshabilitar MDA utilizado una variable de entorno  
 La activación de MDA también puede controlarse mediante la variable de entorno COMPLUS_MDA, que reemplaza la clave del Registro. La cadena COMPLUS_MDA es una lista delimitada por puntos y comas de nombres de MDA u otras cadenas de control especiales, y no distingue entre mayúsculas y minúsculas. Al iniciar bajo un depurador administrado o no administrado se habilita de forma predeterminada un conjunto de MDA. Esto se realiza anteponiendo implícitamente al valor de la variable de entorno o de la clave del Registro la lista delimitada por puntos y comas de los MDA habilitados de manera predeterminada bajo depuradores. Las cadenas de control especiales son las siguientes:  
  
-   `0` - Desactiva todos los MDA.  
  
-   `1`: lee la configuración de MDA de *NombreAplicación*.mda.config.  
  
-   `managedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable administrado bajo un depurador.  
  
-   `unmanagedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable no administrado bajo un depurador.  
  
 Si hay ajustes contradictorios, los más recientes reemplazan los ajustes anteriores:  
  
-   `COMPLUS_MDA=0` deshabilita todos los MDA, incluidos los habilitados implícitamente bajo un depurador.  
  
-   `COMPLUS_MDA=gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` además de los MDA habilitados implícitamente bajo un depurador.  
  
-   `COMPLUS_MDA=0;gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` pero deshabilita los MDA que, de otro modo, estarían habilitados implícitamente bajo un depurador.  
  
<a name="appConfig"></a>   
### <a name="enabling-and-disabling-mdas-by-using-application-specific-configuration-settings"></a>Habilitar y deshabilitar MDA utilizando valores de configuración específicos de la aplicación  
 Puede habilitar, deshabilitar y configurar individualmente algunos asistentes en el archivo de configuración de MDA para la aplicación. Para habilitar el uso de un archivo de configuración de la aplicación para configurar los MDA, es necesario establecer la clave del Registro MDA o la variable de entorno COMPLUS_MDA. El archivo de configuración de la aplicación se encuentra normalmente en el mismo directorio que el archivo ejecutable (.exe) de la aplicación. El nombre de archivo toma el formato *NombreAplicación*.mda.config; por ejemplo, notepad.exe.mda.config. Los asistentes que están habilitados en el archivo de configuración de la aplicación pueden tener atributos o elementos diseñados específicamente para controlar el comportamiento de los citados asistentes. El ejemplo siguiente muestra cómo habilitar y configurar la [serialización](../../../docs/framework/debug-trace-profile/marshaling-mda.md).  
  
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
  
 El MDA de `Marshaling` emite información sobre el tipo administrado cuyas referencias se calculan a un tipo no administrado para cada transición de administrado a no administrado en la aplicación. El MDA de `Marshaling` también puede filtrar los nombres de los campos de método y estructura proporcionados en los elementos secundarios `<methodFilter>` y `<fieldFilter>`, respectivamente.  
  
 En el siguiente ejemplo se muestra cómo habilitar varios MDA utilizando su configuración predeterminada.  
  
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
>  Cuando se especifica más de un asistente en un archivo de configuración, se deben enumerar en orden alfabético. Por ejemplo, si se desea habilitar los MDA `virtualCERCall` e `invalidCERCall`, se debe agregar la entrada `<invalidCERCall />` antes que la entrada `<virtualCERCall />`. Si las entradas no están en orden alfabético, se muestra un mensaje de excepción no controlada de archivo de configuración no válido.  
  
### <a name="mda-output"></a>Salida del MDA  
 El resultado del MDA es similar al ejemplo siguiente, que muestra el resultado del MDA `pInvokeStackImbalance`.  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## <a name="see-also"></a>Vea también  
 [Depurar, trazar y generar perfiles](../../../docs/framework/debug-trace-profile/index.md)
