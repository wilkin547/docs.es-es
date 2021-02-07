---
description: 'Más información acerca de: ICorDebugRegisterSet:: GetThreadContext (método)'
title: ICorDebugRegisterSet::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: be6384562858d04b6e139eda83c172c09f2dfc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690813"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext (Método)

Obtiene el contexto del subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `contextSize`  
 de Tamaño, en bytes, de la `context` matriz.  
  
 `context`  
 [in, out] Matriz de bytes que componen la `CONTEXT` estructura de Win32 para la plataforma actual.  
  
## <a name="remarks"></a>Observaciones  

 El depurador debe llamar a esta función en lugar de a la función de Win32 `GetThreadContext` , ya que el subproceso puede estar en un estado "secuestrado" donde su contexto ha cambiado temporalmente. Los datos devueltos son una `CONTEXT` estructura Win32 para la plataforma actual.  
  
 En el caso de los marcos no hoja, los clientes deben comprobar qué registros son válidos mediante [ICorDebugRegisterSet:: getregistersavailable (](icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet (Interfaz)](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)
