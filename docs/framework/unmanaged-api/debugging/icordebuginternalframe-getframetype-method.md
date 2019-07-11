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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760045"
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
 [out] Un puntero a un valor de la enumeración CorDebugInternalFrameType que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de marco interno nunca será STUBFRAME_NONE. Los depuradores deberían omitir correctamente los tipos de marco interno no reconocido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
