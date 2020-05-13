---
title: ICorDebugModule::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212521"
---
# <a name="icordebugmodulegetsize-method"></a>ICorDebugModule::GetSize (Método)
Obtiene el tamaño, en bytes, del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pcBytes`  
 enuncia Tamaño del módulo en bytes.  
  
 Si el módulo se generó a partir del generador de imágenes nativas (NGen. exe), el tamaño del módulo será cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
