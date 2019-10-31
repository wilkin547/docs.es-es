---
title: ICorPublishProcess::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103500"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged (Método)
Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) tiene código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbManaged`  
 enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado. El valor es `true` si el proceso tiene código administrado; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Dado que la versión actual de `ICorPublishProcess` permite el acceso únicamente a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublishProcess (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
