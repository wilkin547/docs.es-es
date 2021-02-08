---
description: 'Más información sobre: ICorDebugThread3:: CreateStackWalk ((método)'
title: ICorDebugThread3::CreateStackWalk (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: b36252160dbad14ca1bee0674b6d042072a36359
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800999"
---
# <a name="icordebugthread3createstackwalk-method"></a>ICorDebugThread3::CreateStackWalk (Método)

Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppStackWalk`  
 enuncia Puntero a la dirección del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El `ICorDebugStackWalk` objeto se ha creado correctamente.|  
|E_FAIL|`ICorDebugStackWalk`No se creó el objeto.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  

 Si el `CreateStackWalk` método se ejecuta correctamente, el `ICorDebugStackWalk` contexto del objeto devuelto se establece en el contexto actual del subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
