---
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 62773ce526b1f21c57ab85a106708589fcf92f6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138269"
---
# <a name="deprecated-clr-hosting-functions"></a>Funciones de hospedaje de CLR en desuso
En esta sección se describen las funciones estáticas globales no administradas que usaban versiones anteriores de la API de hospedaje.  
  
 A excepción de las funciones de infraestructura (funciones de`_Cor*`), que solo se usan en el .NET Framework, estas funciones han quedado en desuso en el .NET Framework 4.  
  
## <a name="activation-functions"></a>Funciones de activación  
 [ClrCreateManagedInstance (función)](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Desusado. Crea una instancia del tipo administrado especificado.  
  
 [CoInitializeCor (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleto. Para inicializar el Common Language Runtime (CLR), use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Desusado. Garantiza que el motor de ejecución de CLR se carga en un proceso. Use en su lugar el método [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .  
  
 [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Desusado. Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.  
  
 [CorBindToRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso.  
  
 [CorBindToRuntimeByCfg (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Desusado. Carga el CLR en un proceso utilizando la información de versión que se lee de un archivo XML.  
  
 [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Desusado. Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.  
  
 [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Desusado. Permite a los hosts cargar una versión especificada de CLR en un proceso.  
  
 [GetCORRequiredVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Desusado. Obtiene el número de versión de CLR requerido.  
  
 [GetCORSystemDirectory (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Desusado. Devuelve el directorio de instalación de CLR que se carga en el proceso.  
  
 [GetRealProcAddress (Función)](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Desusado. Obtiene la dirección de la función especificada que se exporta de la última versión instalada de CLR.  
  
 [GetRequestedRuntimeInfo (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Desusado. Obtiene información de versión y directorio sobre el CLR solicitado por una aplicación.  
  
## <a name="clr-version-functions"></a>Funciones de versión de CLR  
 Las funciones de esta sección devuelven una versión de CLR; no activan el CLR.  
  
 [GetCORVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Desusado. Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.  
  
 [GetFileVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Desusado. Obtiene la información de versión de CLR del archivo especificado, utilizando el búfer especificado.  
  
 [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Desusado. Obtiene el número de versión de CLR solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.  
  
 [GetRequestedRuntimeVersionForCLSID (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Desusado. Obtiene la información de versión de CLR adecuada para la clase con el CLSID especificado.  
  
 [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Desusado. Obtiene el número de versión de CLR que está asociado al identificador de proceso especificado.  
  
 [LockClrVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Desusado. Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar explícitamente CLR.  
  
## <a name="hosting-functions"></a>Funciones de hospedaje  
 [CallFunctionShim (función)](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Desusado. Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.  
  
 [CoEEShutDownCOM (función)](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Desusado. Descarga un ensamblado COM del proceso.  
  
 [CorExitProcess (función)](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Desusado. Cierra el proceso no administrado actual.  
  
 [CorLaunchApplication (función)](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Desusado. Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.  
  
 [CorMarkThreadInThreadPool (función)](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Desusado. Marca el subproceso de grupo de subprocesos que se está ejecutando actualmente para la ejecución de código administrado. A partir de la versión 2,0 de .NET Framework, esta función no tiene ningún efecto. No es necesario y se puede quitar del código.  
  
 [CoUninitializeCor (función)](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleto. CLR no se puede descargar de un proceso.  
  
 [CoUninitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleto.  
  
 [CreateDebuggingInterfaceFromVersion (función)](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Desusado. Crea un objeto [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 [CreateICeeFileGen (función)](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Desusado. Crea un objeto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [DestroyICeeFileGen (función)](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Desusado. Destruye un objeto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [Puntero a la función FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Desusado. Apunta a una función a la que CLR llama para ejecutar código administrado.  
  
 [Puntero a la función FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Desusado. Apunta a una función a la que CLR llama para notificar al host que la inicialización se ha iniciado o completado.  
  
 [GetCLRIdentityManager (función)](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Desusado. Obtiene un puntero a una interfaz que permite a CLR administrar las identidades.  
  
 [LoadLibraryShim (Función)](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Desusado. Carga una versión especificada de un .NET Framework DLL.  
  
 [LoadStringRC (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.  
  
 [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Desusado. Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 [Puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.  
  
 [Puntero a la función LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.  
  
 [RunDll32ShimW (Función)](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Desusado. Ejecuta el comando especificado.  
  
 [Puntero a la función WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Desusado. Apunta a una función que notifica al host que un identificador de espera se ha señalado o ha agotado el tiempo de espera.  
  
## <a name="infrastructure-functions"></a>Funciones de infraestructura  
 Las funciones de esta sección solo las pueden usar los .NET Framework.  
  
 [_CorDllMain (función)](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.  
  
 [_CorExeMain (función)](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.  
  
 [_CorExeMain2 (función)](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Ejecuta el punto de entrada en el código asignado a la memoria especificado. El cargador del sistema operativo llama a esta función.  
  
 [_CorImageUnloading (función)](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al cargador cuando se descargan las imágenes del módulo administrado.  
  
 [_CorValidateImage (función)](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de hospedaje de .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
