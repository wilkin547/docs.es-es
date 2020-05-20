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
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421103"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged (Método)
Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbManaged`  
 enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado. El valor es `true` si el proceso tiene código administrado; de lo contrario, es `false` .  
  
## <a name="remarks"></a>Observaciones  
 Dado que la versión actual de `ICorPublishProcess` solo permite el acceso a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICorPublishProcess (Interfaz)](icorpublishprocess-interface.md)
