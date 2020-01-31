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
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790526"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged (Método)
Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pbManaged`  
 enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado. El valor es `true` si el proceso tiene código administrado; de lo contrario, `false`.  
  
## <a name="remarks"></a>Notas  
 Dado que la versión actual de `ICorPublishProcess` permite el acceso únicamente a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublishProcess (interfaz)](icorpublishprocess-interface.md)
