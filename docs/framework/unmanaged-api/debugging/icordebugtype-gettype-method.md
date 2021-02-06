---
description: 'Más información acerca de: ICorDebugType:: GetType (método)'
title: ICorDebugType::GetType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 922791e51855badfb1fd548e08953a2f660f971a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658222"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType (Método)

Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime (CLR) <xref:System.Type> representado por esta ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ty`  
 enuncia Un puntero a un valor de la `CorElementType` enumeración que indica el CLR <xref:System.Type> que este `ICorDebugType` representa.  
  
## <a name="remarks"></a>Observaciones  

 Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, se puede llamar al método [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) para obtener el tipo sin instancia de un tipo genérico; de lo contrario, no se llama a `ICorDebugType::GetClass` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
