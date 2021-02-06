---
description: 'Más información sobre: ICLRDebugManager:: Getdacl ((método)'
title: ICLRDebugManager::GetDacl (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: 8a1b747851d0c5104dbe18e5a66742d57b09aa22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649486"
---
# <a name="iclrdebugmanagergetdacl-method"></a>ICLRDebugManager::GetDacl (Método)

Este método no se implementa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppacl`  
 enuncia Puntero de interfaz a la lista de Access Control (ACL).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|E_NOTIMPL|El método no está implementado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLRDebugManager (Interfaz)](iclrdebugmanager-interface.md)
- [Método SetDacl](iclrdebugmanager-setdacl-method.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
