---
title: ICorDebugStepper::Deactivate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730596"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate (Método)

Hace que este ICorDebugStepper cancele el último comando de paso que recibió.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Comentarios  

 Es posible que se emita un nuevo comando de paso A paso después de que se haya cancelado el comando de paso recibido más recientemente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
