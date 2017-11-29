---
title: "IGCThreadControl::SuspensionEnding (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4460d2b0eaf10d20ddd0c3641279a8ffc05c245
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionending-method"></a>IGCThreadControl::SuspensionEnding (Método)
Notifica al host que el runtime está reanudando los subprocesos después de una colección de elementos no utilizados u otra suspensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Generation`  
 [in] La generación en la que se ha realizado una recolección de elementos.  
  
## <a name="remarks"></a>Comentarios  
 No volver a programar todos los subprocesos durante la `SuspensionEnding` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IGCThreadControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
