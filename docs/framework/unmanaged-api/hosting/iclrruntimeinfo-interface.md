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
ms.openlocfilehash: f6608b03df80fa37ebf5049b53bce46da3e155e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120370"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo (Interfaz)
Proporciona métodos que devuelven información sobre un Common Language Runtime específico (CLR), incluidos la versión, el directorio y el estado de carga. Esta interfaz también proporciona funcionalidad específica en tiempo de ejecución sin inicializar el tiempo de ejecución. Incluye el método [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) relativo en tiempo de ejecución, el método [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) específico del módulo en tiempo de ejecución y las interfaces proporcionadas por el tiempo de ejecución mediante el método [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Enlaza este Runtime para todas las decisiones de directiva de activación heredadas de la versión 2 de CLR.|  
|[GetDefaultStartupFlags (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Obtiene las marcas de inicio y el archivo de configuración de host de CLR.|  
|[GetInterface (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución, como [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) e [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Este método sustituye todas las funciones de `CorBindTo*`.|  
|[GetProcAddress (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Obtiene la dirección de una función especificada que se exportó desde el CLR asociado a esta interfaz. Este método reemplaza el método [GetRealProcAddress (](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) .|  
|[GetRuntimeDirectory (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Obtiene el directorio de instalación de CLR asociado a esta interfaz. Este método reemplaza el método [GetCORSystemDirectory (](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) .|  
|[GetVersionString (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Obtiene la información de versión de Common Language Runtime (CLR) asociada a una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) especificada. Este método sustituye a los métodos [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) y [GetRequestedRuntimeVersion (](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) .|  
|[IsLoadable (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que podrían haberse cargado en el proceso.|  
|[IsLoaded (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Indica si el CLR asociado a la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) se carga en un proceso.|  
|[IsStarted (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Indica si se ha iniciado el CLR asociado a la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .|  
|[LoadErrorString (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada. Este método sustituye a los métodos [loadstringrc (](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) y [loadstringrcex (](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) .|  
|[LoadLibrary (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Carga una biblioteca desde el directorio de .NET Framework del CLR representado por una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) . Este método reemplaza el método [LoadLibraryShim (](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) .|  
|[SetDefaultStartupFlags (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Establece las marcas de inicio y el archivo de configuración de host de CLR.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
