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
ms.openlocfilehash: d86f9b4903663604094895f6747b1407ff98c990
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="deprecated-clr-hosting-functions"></a>Funciones de hospedaje de CLR en desuso
Esta sección describen las funciones estáticas globales no administradas que utiliza versiones anteriores de la API de hospedaje.  
  
 Con la excepción de las funciones de infraestructura (`_Cor*` funciones), que se usa únicamente con .NET Framework, estas funciones han quedado obsoletas en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Funciones de activación  
 [ClrCreateManagedInstance (función)](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Desusado. Crea una instancia del tipo administrado especificado.  
  
 [CoInitializeCor (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleto. Para inicializar common language runtime (CLR), use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Desusado. Garantiza que el motor de ejecución de CLR se carga en un proceso. Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.  
  
 [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Desusado. Carga common language runtime (CLR) en un proceso usando la información de versión almacenada en un archivo XML.  
  
 [CorBindToRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Desusado. Permite que los hosts no administrados cargar CLR en un proceso.  
  
 [CorBindToRuntimeByCfg (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Desusado. Carga el CLR en un proceso mediante el uso de información de versión que se lee desde un archivo XML.  
  
 [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.  
  
 [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Desusado. Permite a los hosts cargar una versión especificada de CLR en un proceso.  
  
 [GetCORRequiredVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Desusado. Obtiene el número de versión CLR necesario.  
  
 [GetCORSystemDirectory (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Desusado. Devuelve el directorio de instalación de CLR que se carga en el proceso.  
  
 [GetRealProcAddress (Función)](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Desusado. Obtiene la dirección de la función especificada que se exporta desde la última versión instalada de CLR.  
  
 [GetRequestedRuntimeInfo (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Desusado. Obtiene información de versión y directorio acerca del entorno CLR solicitado por una aplicación.  
  
## <a name="clr-version-functions"></a>Funciones de la versión CLR  
 Las funciones de esta sección devuelven una versión CLR; no activa el CLR.  
  
 [GetCORVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Desusado. Devuelve el número de versión de CLR que se ejecuta en el proceso actual.  
  
 [GetFileVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Desusado. Obtiene la información de versión CLR del archivo especificado, utilizando el búfer especificado.  
  
 [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Desusado. Obtiene el número de versión de CLR solicitado por la aplicación especificada. Si no está instalada esa versión, obtiene la versión más reciente que esté instalada antes de la versión solicitada.  
  
 [GetRequestedRuntimeVersionForCLSID (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Desusado. Obtiene la información de versión CLR correspondiente para la clase con el CLSID especificado.  
  
 [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Desusado. Obtiene el número de versión de CLR que está asociado con el identificador de proceso especificado.  
  
 [LockClrVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Desusado. Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar el CLR de forma explícita.  
  
## <a name="hosting-functions"></a>Funciones de hospedaje  
 [CallFunctionShim (función)](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Desusado. Realiza una llamada a la función que tiene el nombre especificado y los parámetros en la biblioteca especificada.  
  
 [CoEEShutDownCOM (función)](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Desusado. Descarga un ensamblado COM del proceso.  
  
 [CorExitProcess (función)](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Desusado. Se cierra el proceso actual no administrado.  
  
 [CorLaunchApplication (función)](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Desusado. Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.  
  
 [CorMarkThreadInThreadPool (función)](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Desusado. Marca el subproceso actualmente en ejecución del grupo de subprocesos para la ejecución de código administrado. A partir de la versión 2.0 de .NET Framework, esta función no tiene ningún efecto. No es necesario y puede quitarse desde el código.  
  
 [CoUninitializeCor (función)](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleto. El CLR no se puede descargar desde un proceso.  
  
 [CoUninitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleto.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Desusado. Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.  
  
 [CreateICeeFileGen (función)](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Desusado. Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.  
  
 [DestroyICeeFileGen (función)](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Desusado. Destruye una [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.  
  
 [Puntero a la función FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Desusado. Señala a una función que llama a CLR para ejecutar código administrado.  
  
 [Puntero a la función FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Desusado. Señala a una función que CLR llama para notificar al host que la inicialización se ha iniciado o completado.  
  
 [GetCLRIdentityManager (función)](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Desusado. Obtiene un puntero a una interfaz que permite a CLR administrar identidades.  
  
 [LoadLibraryShim (Función)](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Desusado. Carga la versión especificada de una DLL de .NET Framework.  
  
 [LoadStringRC (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.  
  
 [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Desusado. Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.  
  
 [Puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Desusado. Señala a una función que notifica al host cuándo una superposición (es decir, asincrónica) ha completado la E/S en un dispositivo.  
  
 [Puntero a la función LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Desusado. Señala a una función que notifica al host que ha empezado a ejecutar un subproceso.  
  
 [RunDll32ShimW (Función)](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Desusado. Ejecuta el comando especificado.  
  
 [Puntero a la función WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Desusado. Señala a una función que notifica al host que un identificador de espera se ha señalado o agotó el tiempo.  
  
## <a name="infrastructure-functions"></a>Funciones de infraestructura  
 Las funciones de esta sección son para uso sólo .NET Framework.  
  
 [_CorDllMain (función)](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de la DLL y comienza la ejecución.  
  
 [_CorExeMain (función)](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
 [_CorExeMain2 (función)](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Ejecuta el punto de entrada en el código asignado a la memoria especificado. Esta función se invoca por el cargador del sistema operativo.  
  
 [_CorImageUnloading (función)](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al cargador cuándo se descargan imágenes del módulo administrado.  
  
 [_CorValidateImage (función)](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Valida las imágenes del módulo administrado y notifica el cargador del sistema operativo después de que se han cargado.  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales de hospedaje de .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
