---
title: IHostMemoryManager::AcquiredVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67fc415f1569abd35819d7b3a59459052e3591ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486139"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>IHostMemoryManager::AcquiredVirtualAddressSpace (Método)
Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada desde el sistema operativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `startAddress`  
 [in] La dirección inicial de la memoria.  
  
 `size`  
 [in] El tamaño, en bytes, de la memoria.  
  
## <a name="remarks"></a>Comentarios  
 El `AcquiredVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación de hospedaje. Se llama a CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
