---
title: ICorDebugClass2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717830"
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus (Método)

Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `bIsJustMyCode`  
 de Se establece en `true` para indicar que el método es código definido por el usuario; de lo contrario, se establece en `false` .  
  
## <a name="remarks"></a>Comentarios  

 Un stepper de solo mi código (JMC) omitirá el código no definido por el usuario. El código definido por el usuario debe ser un subconjunto del código depurable.  
  
 `SetJMCStatus` Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor para ningún método, aunque establezca correctamente el valor de todos los demás métodos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
