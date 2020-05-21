---
title: ICLRRuntimeInfo (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
ms.openlocfilehash: cafb85ed5f6a1245dd520ab3a5e94f95c8d37608
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762557"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo (Interfaz)
Proporciona métodos que devuelven información sobre un Common Language Runtime específico (CLR), incluidos la versión, el directorio y el estado de carga. Esta interfaz también proporciona funcionalidad específica en tiempo de ejecución sin inicializar el tiempo de ejecución. Incluye el método [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) relativo en tiempo de ejecución, el método [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) específico del módulo en tiempo de ejecución y las interfaces proporcionadas por el tiempo de ejecución mediante el método [GetInterface](iclrruntimeinfo-getinterface-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Enlaza este Runtime para todas las decisiones de directiva de activación heredadas de la versión 2 de CLR.|  
|[Método GetDefaultStartupFlags](iclrruntimeinfo-getdefaultstartupflags-method.md)|Obtiene las marcas de inicio y el archivo de configuración de host de CLR.|  
|[Método GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución, como [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) e [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Este método sustituye todas las `CorBindTo*` funciones.|  
|[Método GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Obtiene la dirección de una función especificada que se exportó desde el CLR asociado a esta interfaz. Este método reemplaza el método [GetRealProcAddress (](getrealprocaddress-function.md) .|  
|[Método GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Obtiene el directorio de instalación de CLR asociado a esta interfaz. Este método reemplaza el método [GetCORSystemDirectory (](getcorsystemdirectory-function.md) .|  
|[GetVersionString (Método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Obtiene la información de versión de Common Language Runtime (CLR) asociada a una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) especificada. Este método sustituye a los métodos [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) y [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md) .|  
|[Método IsLoadable](iclrruntimeinfo-isloadable-method.md)|Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que podrían haberse cargado en el proceso.|  
|[Método IsLoaded](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Indica si el CLR asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) se carga en un proceso.|  
|[Método IsStarted](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Indica si se ha iniciado el CLR asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .|  
|[Método LoadErrorString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada. Este método sustituye a los métodos [loadstringrc (](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) y [loadstringrcex (](loadstringrcex-function.md) .|  
|[Método LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Carga una biblioteca desde el directorio de .NET Framework del CLR representado por una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) . Este método reemplaza el método [LoadLibraryShim (](loadlibraryshim-function.md) .|  
|[Método SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)|Establece las marcas de inicio y el archivo de configuración de host de CLR.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
