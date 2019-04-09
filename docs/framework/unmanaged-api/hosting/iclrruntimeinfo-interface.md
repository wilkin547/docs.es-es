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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 213fa9fda6b154d4548b4163cc7b5890bfcfb49c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186997"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo (Interfaz)
Proporciona métodos que devuelven información sobre un específico common language runtime (CLR), incluida la versión, el directorio y el estado de carga. Esta interfaz también proporciona funcionalidad específica del tiempo de ejecución sin inicializar el tiempo de ejecución. Incluye el tiempo de ejecución relativa [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) método, el tiempo de ejecución específicas del módulo [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) método y las interfaces proporcionadas en tiempo de ejecución a través de la [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)método.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Enlaza este tiempo de ejecución para todos los heredados CLR versión 2 activación las decisiones de directiva.|  
|[Método GetDefaultStartupFlags](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Obtiene las marcas de inicio CLR y el archivo de configuración de host.|  
|[Método GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución como [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) y [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Este método reemplaza todos los `CorBindTo*` funciones.|  
|[Método GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Obtiene la dirección de una función especificada que se exportó desde el CLR asociado a esta interfaz. Este método reemplaza el [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) método.|  
|[Método GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Obtiene el directorio de instalación de CLR asociado a esta interfaz. Este método reemplaza el [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) método.|  
|[Método GetVersionString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Obtiene la información de versión de common language runtime (CLR) asociado a un determinado [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz. Este método reemplaza el [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) y [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) métodos.|  
|[Método IsLoadable](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que ya es posible que cargarán en el proceso.|  
|[Método IsLoaded](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Indica si el CLR asociados con el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz se carga en un proceso.|  
|[Método IsStarted](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Indica si el CLR que está asociado el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz se ha iniciado.|  
|[Método LoadErrorString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada. Este método reemplaza el [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) y [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) métodos.|  
|[Método LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Carga una biblioteca desde el directorio del marco de trabajo de CLR representado por un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz. Este método reemplaza el [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) método.|  
|[Método SetDefaultStartupFlags](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Establece las marcas de inicio CLR y el host archivo de configuración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md)
