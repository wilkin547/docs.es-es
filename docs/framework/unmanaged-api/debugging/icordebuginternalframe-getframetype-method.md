---
title: ICorDebugInternalFrame::GetFrameType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: 6b598352f734cf47514a82de1d0fca65d430a9ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209973"
---
# <a name="icordebuginternalframegetframetype-method"></a>ICorDebugInternalFrame::GetFrameType (Método)
Obtiene el tipo de este marco interno.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pType`  
 enuncia Un puntero a un valor de la enumeración CorDebugInternalFrameType (que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.  
  
## <a name="remarks"></a>Observaciones  
 El tipo de marco interno nunca se STUBFRAME_NONE. Los depuradores deben omitir correctamente los tipos de Marcos internos no reconocidos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
