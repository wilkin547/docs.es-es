---
description: 'Más información sobre: ICorPublishProcess:: IsManaged ((método)'
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
ms.openlocfilehash: 55f620a896efd87c2f154ac68ef2db1a1b0a1ebc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790508"
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
  
## <a name="see-also"></a>Vea también

- [ICorPublishProcess (Interfaz)](icorpublishprocess-interface.md)
