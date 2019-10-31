---
title: ICLRMetaHost (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb760f4923cc3530a28bc68180db743ee468b51d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140912"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost (Interfaz)
Proporciona métodos que devuelven una versión específica del Common Language Runtime (CLR) en función de su número de versión, enumeran todos los CLR instalados, enumeran todos los Runtimes que se cargan en un proceso especificado, detectan la versión de CLR que se usa para compilar un ensamblado, salir de un proceso. con un cierre en tiempo de ejecución limpio y consultas de enlace de API heredado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) válido para cada versión de CLR que está instalada en un equipo.|  
|[EnumerateLoadedRuntimes (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) válido para cada CLR que se carga en un proceso determinado. Este método reemplaza a [GetVersionFromProcess (](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).|  
|[ExitProcess (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso. Reemplaza la función [CorExitProcess (](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) .|  
|[GetRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Obtiene la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) que corresponde a una versión de CLR determinada. Este método reemplaza a la función [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .|  
|[GetVersionFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Obtiene la versión de compilación original .NET Framework del ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo. Este método reemplaza a [GetFileVersion (](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).|  
|[QueryLegacyV2RuntimeBinding (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el atributo `useLegacyV2RuntimeActivationPolicy` en la entrada\<archivo de configuración del [elemento > de inicio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o mediante llamada al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) .|  
|[RequestRuntimeLoadedNotification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Garantiza una devolución de llamada al puntero de función especificado cuando se carga por primera vez una versión de CLR, pero aún no se ha iniciado. Este método reemplaza a [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>Comentarios  
 La única forma de obtener una instancia de esta interfaz es mediante una llamada a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) de la siguiente manera:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
