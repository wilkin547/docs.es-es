---
title: ICorDebugReferenceValue::Dereference (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 6bb2a6b68a3c6e981a2d6c833d3f44d4c836bd23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124010"
---
# <a name="icordebugreferencevaluedereference-method"></a>ICorDebugReferenceValue::Dereference (Método)
Obtiene el objeto al que se hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el objeto al que señala este objeto ICorDebugReferenceValue.  
  
## <a name="remarks"></a>Comentarios  
 El objeto `ICorDebugValue` solo es válido mientras su referencia todavía no se ha deshabilitado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
