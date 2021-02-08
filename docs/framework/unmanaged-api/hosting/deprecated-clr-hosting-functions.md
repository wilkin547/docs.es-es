---
description: 'Más información sobre: funciones de hospedaje de CLR en desuso'
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 3d16b5829e29c5c963f4790bbb3be7adcaeedbfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785671"
---
# <a name="deprecated-clr-hosting-functions"></a>Funciones de hospedaje de CLR en desuso

En esta sección se describen las funciones estáticas globales no administradas que usaban versiones anteriores de la API de hospedaje.  
  
 A excepción de las funciones de infraestructura ( `_Cor*` funciones), que solo se usan en el .NET Framework, estas funciones han quedado en desuso en el .NET Framework 4.  
  
## <a name="activation-functions"></a>Funciones de activación  

 [ClrCreateManagedInstance (Función)](clrcreatemanagedinstance-function.md)  
 En desuso. Crea una instancia del tipo administrado especificado.  
  
 [CoInitializeCor (Función)](coinitializecor-function.md)  
 Obsoleto. Para inicializar el Common Language Runtime (CLR), use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (Función)](coinitializeee-function.md)  
 En desuso. Garantiza que el motor de ejecución de CLR se carga en un proceso. Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
 [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)  
 En desuso. Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.  
  
 [CorBindToRuntime (Función)](corbindtoruntime-function.md)  
 En desuso. Permite a los hosts no administrados cargar CLR en un proceso.  
  
 [CorBindToRuntimeByCfg (Función)](corbindtoruntimebycfg-function.md)  
 En desuso. Carga el CLR en un proceso utilizando la información de versión que se lee de un archivo XML.  
  
 [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)  
 En desuso. Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.  
  
 [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)  
 En desuso. Permite a los hosts cargar una versión especificada de CLR en un proceso.  
  
 [GetCORRequiredVersion (Función)](getcorrequiredversion-function.md)  
 En desuso. Obtiene el número de versión de CLR requerido.  
  
 [GetCORSystemDirectory (Función)](getcorsystemdirectory-function.md)  
 En desuso. Devuelve el directorio de instalación de CLR que se carga en el proceso.  
  
 [GetRealProcAddress (Función)](getrealprocaddress-function.md)  
 En desuso. Obtiene la dirección de la función especificada que se exporta de la última versión instalada de CLR.  
  
 [GetRequestedRuntimeInfo (Función)](getrequestedruntimeinfo-function.md)  
 En desuso. Obtiene información de versión y directorio sobre el CLR solicitado por una aplicación.  
  
## <a name="clr-version-functions"></a>Funciones de versión de CLR  

 Las funciones de esta sección devuelven una versión de CLR; no activan el CLR.  
  
 [GetCORVersion (Función)](getcorversion-function.md)  
 En desuso. Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.  
  
 [GetFileVersion (Función)](getfileversion-function.md)  
 En desuso. Obtiene la información de versión de CLR del archivo especificado, utilizando el búfer especificado.  
  
 [GetRequestedRuntimeVersion (Función)](getrequestedruntimeversion-function.md)  
 En desuso. Obtiene el número de versión de CLR solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.  
  
 [GetRequestedRuntimeVersionForCLSID (Función)](getrequestedruntimeversionforclsid-function.md)  
 En desuso. Obtiene la información de versión de CLR adecuada para la clase con el CLSID especificado.  
  
 [GetVersionFromProcess (Función)](getversionfromprocess-function.md)  
 En desuso. Obtiene el número de versión de CLR que está asociado al identificador de proceso especificado.  
  
 [LockClrVersion (Función)](lockclrversion-function.md)  
 En desuso. Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar explícitamente CLR.  
  
## <a name="hosting-functions"></a>Funciones de hospedaje  

 [CallFunctionShim (Función)](callfunctionshim-function.md)  
 En desuso. Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.  
  
 [CoEEShutDownCOM (Función)](coeeshutdowncom-function.md)  
 En desuso. Descarga un ensamblado COM del proceso.  
  
 [CorExitProcess (Función)](corexitprocess-function.md)  
 En desuso. Cierra el proceso no administrado actual.  
  
 [CorLaunchApplication (Función)](corlaunchapplication-function.md)  
 En desuso. Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.  
  
 [CorMarkThreadInThreadPool (Función)](cormarkthreadinthreadpool-function.md)  
 En desuso. Marca el subproceso de grupo de subprocesos que se está ejecutando actualmente para la ejecución de código administrado. A partir de la versión 2,0 de .NET Framework, esta función no tiene ningún efecto. No es necesario y se puede quitar del código.  
  
 [CoUninitializeCor (Función)](couninitializecor-function.md)  
 Obsoleto. CLR no se puede descargar de un proceso.  
  
 [CoUninitializeEE (Función)](couninitializeee-function.md)  
 Obsoleto.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](createdebugginginterfacefromversion-function.md)  
 En desuso. Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 [CreateICeeFileGen (Función)](createiceefilegen-function.md)  
 En desuso. Crea un objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 [DestroyICeeFileGen (Función)](destroyiceefilegen-function.md)  
 En desuso. Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 [puntero a la función FExecuteInAppDomainCallback](fexecuteinappdomaincallback-function-pointer.md)  
 En desuso. Apunta a una función a la que CLR llama para ejecutar código administrado.  
  
 [puntero a la función FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)  
 En desuso. Apunta a una función a la que CLR llama para notificar al host que la inicialización se ha iniciado o completado.  
  
 [GetCLRIdentityManager (Función)](getclridentitymanager-function.md)  
 En desuso. Obtiene un puntero a una interfaz que permite a CLR administrar las identidades.  
  
 [LoadLibraryShim (Función)](loadlibraryshim-function.md)  
 En desuso. Carga una versión especificada de un .NET Framework DLL.  
  
 [LoadStringRC (Función)](loadstringrc-function.md)  
 En desuso. Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.  
  
 [LoadStringRCEx (Función)](loadstringrcex-function.md)  
 En desuso. Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 [puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE](lpoverlapped-completion-routine-function-pointer.md)  
 En desuso. Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.  
  
 [puntero a la función LPTHREAD_START_ROUTINE](lpthread-start-routine-function-pointer.md)  
 En desuso. Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.  
  
 [RunDll32ShimW (Función)](rundll32shimw-function.md)  
 En desuso. Ejecuta el comando especificado.  
  
 [puntero a la función WAITORTIMERCALLBACK](waitortimercallback-function-pointer.md)  
 En desuso. Apunta a una función que notifica al host que un identificador de espera se ha señalado o ha agotado el tiempo de espera.  
  
## <a name="infrastructure-functions"></a>Funciones de infraestructura  

 Las funciones de esta sección solo las pueden usar los .NET Framework.  
  
 [_CorDllMain (Función)](cordllmain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.  
  
 [_CorExeMain (Función)](corexemain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
 [_CorExeMain2 (Función)](corexemain2-function.md)  
 Ejecuta el punto de entrada en el código asignado a la memoria especificado. El cargador del sistema operativo llama a esta función.  
  
 [_CorImageUnloading (Función)](corimageunloading-function.md)  
 Notifica al cargador cuando se descargan las imágenes del módulo administrado.  
  
 [_CorValidateImage (Función)](corvalidateimage-function.md)  
 Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de hospedaje de .NET Framework 4](net-framework-4-hosting-global-static-functions.md)
