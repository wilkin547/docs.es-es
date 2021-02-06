---
description: 'Más información acerca de: ICorDebugType:: GetClass (método)'
title: ICorDebugType::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 2e8d68fbc8909599ca649ba0e226cc84af820939
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658352"
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass (Método)

Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppClass`  
 enuncia Puntero a la dirección de una `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.  
  
## <a name="remarks"></a>Observaciones  

 `GetClass` solo se puede llamar en determinadas condiciones. Llame a [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de llamar a `GetClass` . Si `ICorDebugType::GetType` devuelve un valor de CorElementType que es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar a para obtener el tipo sin instancia para un tipo genérico.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
