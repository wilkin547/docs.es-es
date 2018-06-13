---
title: ICLRRuntimeInfo::IsLoadable (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e60c3b06453e0f447249bddf5d4da5c240576577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432965"
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable (Método)
Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que puede que ya esté cargado en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbLoadable`  
 [out] `true` si este runtime se pudo cargar en el proceso actual; en caso contrario, `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pbLoadable` es null.|  
  
## <a name="remarks"></a>Comentarios  
 Si otro tiempo de ejecución ya se carga en el proceso y el tiempo de ejecución asociado a esta interfaz se puede cargar para la ejecución de en paralelo en proceso, `pbLoadable` devuelve `true`. Si los dos tiempos de ejecución no pueden ejecutar en paralelo en proceso, `pbLoadable` devuelve `false`. Por ejemplo, common language runtime (CLR) versión 4 puede ejecutar en paralelo en el mismo proceso con la versión 2.0 de CLR o CLR versión 1.1. Sin embargo, CLR versión 1.1 y versión 2.0 de CLR no pueden ejecutar en paralelo en proceso.  
  
 Si el tiempo de ejecución no se carga en el proceso, este método devuelve siempre `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
