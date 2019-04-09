---
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa84ca0defd173563817673aad183a8b64226d41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135816"
---
# <a name="deprecated-clr-hosting-functions"></a>Funciones de hospedaje de CLR en desuso
Esta sección describen las funciones estáticas globales no administradas que utiliza las versiones anteriores de la API de hospedaje.  
  
 A excepción de las funciones de infraestructura (`_Cor*` funciones), que se usa solo con .NET Framework, estas funciones han quedado obsoletas en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Funciones de activación  
 [ClrCreateManagedInstance (Función)](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Desusado. Crea una instancia del tipo administrado especificado.  
  
 [CoInitializeCor (Función)](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleto. Para inicializar common language runtime (CLR), use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (Función)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Desusado. Garantiza que el motor de ejecución de CLR se carga en un proceso. Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.  
  
 [CorBindToCurrentRuntime (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Desusado. Carga common language runtime (CLR) en un proceso mediante el uso de información de versión almacenada en un archivo XML.  
  
 [CorBindToRuntime (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Desusado. Habilita hosts no administrados cargar CLR en un proceso.  
  
 [CorBindToRuntimeByCfg (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Desusado. Carga el CLR en un proceso mediante el uso de información de versión que se lee desde un archivo XML.  
  
 [CorBindToRuntimeEx (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso y le permite establecer marcas para especificar el comportamiento de CLR.  
  
 [CorBindToRuntimeHost (Función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Desusado. Permite a los hosts cargar una versión especificada de CLR en un proceso.  
  
 [GetCORRequiredVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Desusado. Obtiene el número de versión CLR necesario.  
  
 [GetCORSystemDirectory (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Desusado. Devuelve el directorio de instalación de CLR que se carga en el proceso.  
  
 [GetRealProcAddress (Función)](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Desusado. Obtiene la dirección de la función especificada a la que se exporta desde la última versión instalada de CLR.  
  
 [GetRequestedRuntimeInfo (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Desusado. Obtiene información de versión y directorio acerca del entorno CLR solicitado por una aplicación.  
  
## <a name="clr-version-functions"></a>Funciones de la versión CLR  
 Las funciones de esta sección devuelven una versión de CLR; no activan CLR.  
  
 [GetCORVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Desusado. Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.  
  
 [GetFileVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Desusado. Obtiene la información de versión CLR del archivo especificado, utilizando el búfer especificado.  
  
 [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Desusado. Obtiene el número de versión de CLR solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente que esté instalada antes de la versión solicitada.  
  
 [GetRequestedRuntimeVersionForCLSID (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Desusado. Obtiene la información de versión CLR apropiada para la clase con el CLSID especificado.  
  
 [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Desusado. Obtiene el número de versión de CLR que está asociado con el identificador de proceso especificado.  
  
 [LockClrVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Desusado. Permite al host determinar qué versión de CLR que se usará dentro del proceso antes de inicializar CLR de forma explícita.  
  
## <a name="hosting-functions"></a>Funciones de hospedaje  
 [CallFunctionShim (Función)](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Desusado. Realiza una llamada a la función que tiene el nombre especificado y los parámetros de la biblioteca especificada.  
  
 [CoEEShutDownCOM (Función)](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Desusado. Descarga un ensamblado COM del proceso.  
  
 [CorExitProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Desusado. Se cierra el proceso no administrado actual.  
  
 [CorLaunchApplication (Función)](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Desusado. Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.  
  
 [CorMarkThreadInThreadPool (Función)](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Desusado. Marca el subproceso de grupo de subprocesos actualmente en ejecución para la ejecución de código administrado. A partir de la versión 2.0 de .NET Framework, esta función tiene ningún efecto. No es necesario y puede quitarse desde el código.  
  
 [CoUninitializeCor (Función)](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleto. El CLR no se puede descargar desde un proceso.  
  
 [CoUninitializeEE (Función)](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleto.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Desusado. Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.  
  
 [CreateICeeFileGen (Función)](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Desusado. Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.  
  
 [DestroyICeeFileGen (Función)](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Desusado. Destruye un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.  
  
 [puntero a la función FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Desusado. Señala una función que CLR llama para ejecutar código administrado.  
  
 [puntero a la función FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Desusado. Señala una función que CLR llama para notificar al host que la inicialización se ha iniciado o completado.  
  
 [GetCLRIdentityManager (Función)](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Desusado. Obtiene un puntero a una interfaz que permite a CLR administrar identidades.  
  
 [LoadLibraryShim (Función)](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Desusado. Carga la versión especificada de una DLL de .NET Framework.  
  
 [LoadStringRC (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.  
  
 [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Desusado. Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.  
  
 [puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Desusado. Señala a una función que notifica al host cuándo una superpuesta (es decir, asincrónica) se ha completado la E/S en un dispositivo.  
  
 [puntero a la función LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Desusado. Señala una función que notifica al host que un subproceso ha empezado a ejecutar.  
  
 [RunDll32ShimW (Función)](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Desusado. Ejecuta el comando especificado.  
  
 [puntero a la función WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Desusado. Señala una función que notifica al host que un identificador de espera se ha señalado o agotó el tiempo.  
  
## <a name="infrastructure-functions"></a>Funciones de infraestructura  
 Las funciones de esta sección son para uso exclusivo de .NET Framework.  
  
 [_CorDllMain (Función)](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado DLL y comienza la ejecución.  
  
 [_CorExeMain (Función)](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
 [_CorExeMain2 (Función)](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Ejecuta el punto de entrada en el código asignado a memoria especificado. El cargador del sistema operativo llama a esta función.  
  
 [_CorImageUnloading (Función)](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al cargador cuándo se descargan las imágenes de módulo administrado.  
  
 [_CorValidateImage (Función)](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Valida las imágenes de módulo administrado y notifica al cargador del sistema operativo después de que se han cargado.  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de hospedaje de .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
