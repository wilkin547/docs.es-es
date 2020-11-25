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
ms.openlocfilehash: 75c8d550e572795a291f4639f9f28bd5214ff188
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714021"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost (Interfaz)

Proporciona métodos que devuelven una versión específica de la Common Language Runtime (CLR) en función de su número de versión, enumeran todos los CLR instalados, enumeran todos los Runtimes que se cargan en un proceso especificado, detectan la versión de CLR usada para compilar un ensamblado, salen un proceso con un apagado limpio del tiempo de ejecución y consulta el enlace de API heredado  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateInstalledRuntimes](iclrmetahost-enumerateinstalledruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión de CLR que está instalada en un equipo.|  
|[Método EnumerateLoadedRuntimes](iclrmetahost-enumerateloadedruntimes-method.md)|Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada CLR que se carga en un proceso determinado. Este método reemplaza a [GetVersionFromProcess (](getversionfromprocess-function.md).|  
|[Método ExitProcess](iclrmetahost-exitprocess-method.md)|Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso. Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .|  
|[Método GetRuntime](iclrmetahost-getruntime-method.md)|Obtiene la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde a una versión de CLR determinada. Este método reemplaza a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .|  
|[Método GetVersionFromFile](iclrmetahost-getversionfromfile-method.md)|Obtiene la versión de compilación original .NET Framework del ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo. Este método reemplaza a [GetFileVersion (](getfileversion-function.md).|  
|[Método QueryLegacyV2RuntimeBinding](iclrmetahost-querylegacyv2runtimebinding-method.md)|Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en la entrada del archivo de configuración del [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o llamando al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .|  
|[Método RequestRuntimeLoadedNotification](iclrmetahost-requestruntimeloadednotification-method.md)|Garantiza una devolución de llamada al puntero de función especificado cuando se carga por primera vez una versión de CLR, pero aún no se ha iniciado. Este método reemplaza a [LockClrVersion](lockclrversion-function.md)|  
  
## <a name="remarks"></a>Comentarios  

 La única forma de obtener una instancia de esta interfaz es mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) de la siguiente manera:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
