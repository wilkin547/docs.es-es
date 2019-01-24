---
title: IHostMemoryManager::NeedsVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4a67e1eb5a257cc6d4e4c9bc8798b61c97fba38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661755"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>IHostMemoryManager::NeedsVirtualAddressSpace (Método)
Notifica al host que common language runtime (CLR) se va a intentar usar la memoria especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `startAddress`  
 [in] La dirección inicial de la memoria.  
  
 `size`  
 [in] El tamaño, en bytes, de la memoria.  
  
## <a name="remarks"></a>Comentarios  
 El `NeedsVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación de hospedaje. Se llama a CLR.  
  
 Si el host no desea que el CLR para utilizar la memoria especificada, puede devolver un HRESULT de E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
