---
title: IGCThreadControl::SuspensionEnding (Método)
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc91ff0676fcec5d614f9d6fa4850eb2c81086b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779494"
---
# <a name="igcthreadcontrolsuspensionending-method"></a>IGCThreadControl::SuspensionEnding (Método)
Notifica al host que el tiempo de ejecución es reanudar subprocesos después de una recolección de elementos u otra suspensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `Generation`  
 [in] La generación en el que se ha realizado una recolección de elementos.  
  
## <a name="remarks"></a>Comentarios  
 No volver a programar los subprocesos durante la `SuspensionEnding` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCThreadControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
