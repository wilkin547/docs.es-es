---
title: ICorDebugEval2::CreateValueForType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793482"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType (Método)
Obtiene un puntero a una nueva ICorDebugValue del tipo especificado, con un valor inicial de cero o null.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pType`  
 de Puntero a un objeto ICorDebugType que representa el tipo.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto `ICorDebugValue` que representa el valor.  
  
## <a name="remarks"></a>Notas  
 `CreateValueForType` generaliza a [ICorDebugEval:: CreateValue (](icordebugeval-createvalue-method.md) permitiéndole especificar un tipo de objeto arbitrario, incluidos los tipos construidos como `List<int>`. El único propósito de este método es generar un valor que se pueda pasar a una evaluación de función.  
  
 El tipo debe ser una clase o un tipo de valor. No se puede usar este método para crear valores de matriz o valores de cadena.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
