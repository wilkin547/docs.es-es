---
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 9e19502672973f292991b72c7ea9b4fdc17f5707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673129"
---
# <a name="deprecated-clr-hosting-functions"></a>Funciones de hospedaje de CLR en desuso

En esta sección se describen las funciones estáticas globales no administradas que usaban versiones anteriores de la API de hospedaje.  
  
 A excepción de las funciones de infraestructura ( `_Cor*` funciones), que solo se usan en el .NET Framework, estas funciones han quedado en desuso en el .NET Framework 4.  
  
## <a name="activation-functions"></a>Funciones de activación  

 [ClrCreateManagedInstance (Función)](clrcreatemanagedinstance-function.md)  
 Desusado. Crea una instancia del tipo administrado especificado.  
  
 [CoInitializeCor (Función)](coinitializecor-function.md)  
 Obsoleto. Para inicializar el Common Language Runtime (CLR), use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (Función)](coinitializeee-function.md)  
 Desusado. Garantiza que el motor de ejecución de CLR se carga en un proceso. Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
 [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)  
 Desusado. Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.  
  
 [CorBindToRuntime (Función)](corbindtoruntime-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso.  
  
 [CorBindToRuntimeByCfg (Función)](corbindtoruntimebycfg-function.md)  
 Desusado. Carga el CLR en un proceso utilizando la información de versión que se lee de un archivo XML.  
  
 [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.  
  
 [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)  
 Desusado. Permite a los hosts cargar una versión especificada de CLR en un proceso.  
  
 [GetCORRequiredVersion (Función)](getcorrequiredversion-function.md)  
 Desusado. Obtiene el número de versión de CLR requerido.  
  
 [GetCORSystemDirectory (Función)](getcorsystemdirectory-function.md)  
 Desusado. Devuelve el directorio de instalación de CLR que se carga en el proceso.  
  
 [GetRealProcAddress (Función)](getrealprocaddress-function.md)  
 Desusado. Obtiene la dirección de la función especificada que se exporta de la última versión instalada de CLR.  
  
 [GetRequestedRuntimeInfo (Función)](getrequestedruntimeinfo-function.md)  
 Desusado. Obtiene información de versión y directorio sobre el CLR solicitado por una aplicación.  
  
## <a name="clr-version-functions"></a>Funciones de versión de CLR  

 Las funciones de esta sección devuelven una versión de CLR; no activan el CLR.  
  
 [GetCORVersion (Función)](getcorversion-function.md)  
 Desusado. Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.  
  
 [GetFileVersion (Función)](getfileversion-function.md)  
 Desusado. Obtiene la información de versión de CLR del archivo especificado, utilizando el búfer especificado.  
  
 [GetRequestedRuntimeVersion (Función)](getrequestedruntimeversion-function.md)  
 Desusado. Obtiene el número de versión de CLR solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.  
  
 [GetRequestedRuntimeVersionForCLSID (Función)](getrequestedruntimeversionforclsid-function.md)  
 Desusado. Obtiene la información de versión de CLR adecuada para la clase con el CLSID especificado.  
  
 [GetVersionFromProcess (Función)](getversionfromprocess-function.md)  
 Desusado. Obtiene el número de versión de CLR que está asociado al identificador de proceso especificado.  
  
 [LockClrVersion (Función)](lockclrversion-function.md)  
 Desusado. Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar explícitamente CLR.  
  
## <a name="hosting-functions"></a>Funciones de hospedaje  

 [CallFunctionShim (Función)](callfunctionshim-function.md)  
 Desusado. Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.  
  
 [CoEEShutDownCOM (Función)](coeeshutdowncom-function.md)  
 Desusado. Descarga un ensamblado COM del proceso.  
  
 [CorExitProcess (Función)](corexitprocess-function.md)  
 Desusado. Cierra el proceso no administrado actual.  
  
 [CorLaunchApplication (Función)](corlaunchapplication-function.md)  
 Desusado. Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.  
  
 [CorMarkThreadInThreadPool (Función)](cormarkthreadinthreadpool-function.md)  
 Desusado. Marca el subproceso de grupo de subprocesos que se está ejecutando actualmente para la ejecución de código administrado. A partir de la versión 2,0 de .NET Framework, esta función no tiene ningún efecto. No es necesario y se puede quitar del código.  
  
 [CoUninitializeCor (Función)](couninitializecor-function.md)  
 Obsoleto. CLR no se puede descargar de un proceso.  
  
 [CoUninitializeEE (Función)](couninitializeee-function.md)  
 Obsoleto.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](createdebugginginterfacefromversion-function.md)  
 Desusado. Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 [CreateICeeFileGen (Función)](createiceefilegen-function.md)  
 Desusado. Crea un objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 [DestroyICeeFileGen (Función)](destroyiceefilegen-function.md)  
 Desusado. Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 [puntero a la función FExecuteInAppDomainCallback](fexecuteinappdomaincallback-function-pointer.md)  
 Desusado. Apunta a una función a la que CLR llama para ejecutar código administrado.  
  
 [puntero a la función FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)  
 Desusado. Apunta a una función a la que CLR llama para notificar al host que la inicialización se ha iniciado o completado.  
  
 [GetCLRIdentityManager (Función)](getclridentitymanager-function.md)  
 Desusado. Obtiene un puntero a una interfaz que permite a CLR administrar las identidades.  
  
 [LoadLibraryShim (Función)](loadlibraryshim-function.md)  
 Desusado. Carga una versión especificada de un .NET Framework DLL.  
  
 [LoadStringRC (Función)](loadstringrc-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.  
  
 [LoadStringRCEx (Función)](loadstringrcex-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 [puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE](lpoverlapped-completion-routine-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.  
  
 [puntero a la función LPTHREAD_START_ROUTINE](lpthread-start-routine-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.  
  
 [RunDll32ShimW (Función)](rundll32shimw-function.md)  
 Desusado. Ejecuta el comando especificado.  
  
 [puntero a la función WAITORTIMERCALLBACK](waitortimercallback-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host que un identificador de espera se ha señalado o ha agotado el tiempo de espera.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales de hospedaje de .NET Framework 4](net-framework-4-hosting-global-static-functions.md)
