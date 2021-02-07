---
description: 'Más información sobre: ICorDebugEval2:: CallParameterizedFunction ((método)'
title: ICorDebugEval2::CallParameterizedFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: f3947d819caf42bc174dbbba4f5054b9fc4ab1f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693829"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction (Método)

Configura una llamada a la ICorDebugFunction especificada, que se puede anidar dentro de una clase cuyo constructor toma <xref:System.Type> parámetros, o bien puede tomar <xref:System.Type> parámetros.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFunction`  
 de Un puntero a un `ICorDebugFunction` objeto que representa la función a la que se va a llamar.  
  
 `nTypeArgs`  
 de El número de argumentos que toma la función.  
  
 `ppTypeArgs`  
 de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de función.  
  
 `nArgs`  
 de Número de valores pasados en la función.  
  
 `ppArgs`  
 de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor pasado en un argumento de función.  
  
## <a name="remarks"></a>Observaciones  

 `CallParameterizedFunction` es como [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , salvo que la función puede estar dentro de una clase con parámetros de tipo, puede tomar parámetros de tipo o ambos. Los argumentos de tipo deben proporcionarse primero para la clase y, a continuación, para la función.  
  
 Si la función está en un dominio de aplicación diferente, se producirá una transición. Sin embargo, todos los argumentos de tipo y valor deben estar en el dominio de aplicación de destino.  
  
 La evaluación de funciones solo se puede realizar en escenarios limitados. Si `CallParameterizedFunction` o `ICorDebugEval::CallFunction` produce un error, el HRESULT devuelto indicará el motivo más general posible del error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
