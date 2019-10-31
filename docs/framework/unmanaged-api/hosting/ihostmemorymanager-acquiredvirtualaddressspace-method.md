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
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136741"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>IHostMemoryManager::AcquiredVirtualAddressSpace (Método)
Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `startAddress`  
 de Dirección inicial de la memoria.  
  
 `size`  
 de Tamaño, en bytes, de la memoria.  
  
## <a name="remarks"></a>Comentarios  
 El método `AcquiredVirtualAddressSpace` es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje. Lo llama el CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
