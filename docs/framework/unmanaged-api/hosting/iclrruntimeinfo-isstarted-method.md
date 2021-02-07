---
description: 'Más información acerca de: ICLRRuntimeInfo:: IsStarted ((método)'
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
ms.openlocfilehash: 22059ecbded9eae9659cdaae8b9b92f2d7df0650
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753853"
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
  
## <a name="remarks"></a>Observaciones  

 Este método no funciona con las versiones de CLR anteriores a la versión de CLR en el .NET Framework 4.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
