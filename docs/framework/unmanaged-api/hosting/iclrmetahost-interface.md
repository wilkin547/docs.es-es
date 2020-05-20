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
ms.openlocfilehash: 391adc6f9fe55ad7ca527ea416956ab013a27b15
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703722"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost (Interfaz)
Proporciona métodos que devuelven una versión específica de la Common Language Runtime (CLR) en función de su número de versión, enumeran todos los CLR instalados, enumeran todos los Runtimes que se cargan en un proceso especificado, detectan la versión de CLR usada para compilar un ensamblado, salen un proceso con un apagado limpio del tiempo de ejecución y consulta el enlace de API heredado  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateInstalledRuntimes](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión de CLR que está instalada en un equipo.|  
|[Método EnumerateLoadedRuntimes](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) válido para cada CLR que se carga en un proceso determinado. Este método reemplaza a [GetVersionFromProcess (](getversionfromprocess-function.md).|  
|[ExitProcess (Método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso. Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .|  
|[Método GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Obtiene la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) que corresponde a una versión de CLR determinada. Este método reemplaza a la función [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .|  
|[Método GetVersionFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Obtiene la versión de compilación original .NET Framework del ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo. Este método reemplaza a [GetFileVersion (](getfileversion-function.md).|  
|[Método QueryLegacyV2RuntimeBinding](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en la entrada del archivo de configuración del [ \< elemento> de inicio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o llamando al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .|  
|[Método RequestRuntimeLoadedNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Garantiza una devolución de llamada al puntero de función especificado cuando se carga por primera vez una versión de CLR, pero aún no se ha iniciado. Este método reemplaza a [LockClrVersion](lockclrversion-function.md)|  
  
## <a name="remarks"></a>Observaciones  
 La única forma de obtener una instancia de esta interfaz es mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) de la siguiente manera:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
