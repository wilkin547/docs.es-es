---
title: ICLRReferenceAssemblyEnum::Get (Método)
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8cfb2f18bcceed3a125ac7876122c02d2267698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436460"
---
# <a name="iclrreferenceassemblyenumget-method"></a>ICLRReferenceAssemblyEnum::Get (Método)
Obtiene la identidad del ensamblado en el índice proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwIndex`  
 [in] Índice de base cero de la identidad del ensamblado para devolver.  
  
 `pwzBuffer`  
 [out] Un búfer que contiene los datos de identidad de ensamblado.  
  
 `pcchBufferSize`  
 [entrada, salida] El tamaño de la `pwzBuffer` búfer.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Get` se devolvió correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` es demasiado pequeño.|  
|ERROR_NO_MORE_ITEMS|La enumeración no contiene más elementos.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `Get` Normalmente se llama dos veces. La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`. La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónicos tras la finalización.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRReferenceAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
