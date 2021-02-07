---
description: 'Más información acerca de: ICLRRuntimeInfo (interfaz)'
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
ms.openlocfilehash: d599c743e5a42801321ea487fdd9e52bfcfaf081
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753866"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo (Interfaz)

Proporciona métodos que devuelven información sobre un Common Language Runtime específico (CLR), incluidos la versión, el directorio y el estado de carga. Esta interfaz también proporciona funcionalidad específica en tiempo de ejecución sin inicializar el tiempo de ejecución. Incluye el método [LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) relativo en tiempo de ejecución, el método [GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) específico del módulo en tiempo de ejecución y las interfaces proporcionadas por el tiempo de ejecución mediante el método [GetInterface](iclrruntimeinfo-getinterface-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Enlaza este Runtime para todas las decisiones de directiva de activación heredadas de la versión 2 de CLR.|  
|[Método GetDefaultStartupFlags](iclrruntimeinfo-getdefaultstartupflags-method.md)|Obtiene las marcas de inicio y el archivo de configuración de host de CLR.|  
|[Método GetInterface](iclrruntimeinfo-getinterface-method.md)|Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución, como [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md) e [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Este método sustituye todas las `CorBindTo*` funciones.|  
|[Método GetProcAddress](iclrruntimeinfo-getprocaddress-method.md)|Obtiene la dirección de una función especificada que se exportó desde el CLR asociado a esta interfaz. Este método reemplaza el método [GetRealProcAddress (](getrealprocaddress-function.md) .|  
|[Método GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md)|Obtiene el directorio de instalación de CLR asociado a esta interfaz. Este método reemplaza el método [GetCORSystemDirectory (](getcorsystemdirectory-function.md) .|  
|[Método GetVersionString](iclrruntimeinfo-getversionstring-method.md)|Obtiene la información de versión de Common Language Runtime (CLR) asociada a una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) especificada. Este método sustituye a los métodos [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md) y [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md) .|  
|[Método IsLoadable](iclrruntimeinfo-isloadable-method.md)|Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que podrían haberse cargado en el proceso.|  
|[Método IsLoaded](iclrruntimeinfo-isloaded-method.md)|Indica si el CLR asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) se carga en un proceso.|  
|[Método IsStarted](iclrruntimeinfo-isstarted-method.md)|Indica si se ha iniciado el CLR asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .|  
|[Método LoadErrorString](iclrruntimeinfo-loaderrorstring-method.md)|Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada. Este método sustituye a los métodos [loadstringrc (](loadstringrc-function.md) y [loadstringrcex (](loadstringrcex-function.md) .|  
|[Método LoadLibrary](iclrruntimeinfo-loadlibrary-method.md)|Carga una biblioteca desde el directorio de .NET Framework del CLR representado por una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) . Este método reemplaza el método [LoadLibraryShim (](loadlibraryshim-function.md) .|  
|[Método SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)|Establece las marcas de inicio y el archivo de configuración de host de CLR.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
