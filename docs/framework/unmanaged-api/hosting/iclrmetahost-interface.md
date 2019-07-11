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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45089d1b64264e000c07603808f0c5fb1263b042
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776577"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost (Interfaz)
Proporciona métodos que devuelven una versión concreta de common language runtime (CLR) en función de su número de versión, enumerar todos los CLR instalados, lista de todos los runtimes que se cargan en un proceso especificado, detección la versión CLR utilizada para compilar un ensamblado, sale de un proceso con un apagado limpio en tiempo de ejecución y el enlace de API de consulta heredado.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada versión CLR que está instalado en un equipo.|  
|[EnumerateLoadedRuntimes (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada CLR que se carga en un proceso determinado. Este método reemplaza a [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).|  
|[ExitProcess (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso. Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.|  
|[GetRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Obtiene el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que corresponde a una versión determinada de CLR. Este método reemplaza el [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función que se usa con el [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) marca.|  
|[GetVersionFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Obtiene .NET Framework versión de compilación original del ensamblado (almacenada en los metadatos), dada su ruta de acceso de archivo. Este método reemplaza a [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).|  
|[QueryLegacyV2RuntimeBinding (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Devuelve una interfaz que representa un tiempo de ejecución a la que la directiva de activación heredada se ha enlazado, por ejemplo mediante el uso de la `useLegacyV2RuntimeActivationPolicy` atributo el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) entrada del archivo de configuración mediante el uso directo de la API de activación heredadas o llamando a la [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) método.|  
|[RequestRuntimeLoadedNotification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Cuando una versión de CLR se carga por primera vez, pero aún no se ha iniciado, garantiza una devolución de llamada al puntero de función especificado. Este método reemplaza [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>Comentarios  
 La única manera de obtener una instancia de esta interfaz es mediante una llamada a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funcione como se indica a continuación:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
