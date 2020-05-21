---
title: ICLRRuntimeInfo::IsStarted (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 85a7adddf395e07297c8fb6ceab4aa81e0aaf012
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762206"
---
# <a name="iclrruntimeinfoisstarted-method"></a>ICLRRuntimeInfo::IsStarted (Método)
Indica si se ha iniciado el Runtime (es decir, si se ha llamado al [método ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) y se ha realizado correctamente).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbStarted`  
 [out] `true` Si se inicia este Runtime; en caso contrario, `false` .  
  
 `pdwStartupFlags`  
 enuncia Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_NOTIMPL|La versión de Common Language Runtime (CLR) es anterior a la versión de CLR en el .NET Framework 4.|  
  
## <a name="remarks"></a>Comentarios  
 Este método no funciona con las versiones de CLR anteriores a la versión de CLR en el .NET Framework 4.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
