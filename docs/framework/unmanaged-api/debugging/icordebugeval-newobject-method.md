---
title: ICorDebugEval::NewObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: e9570d3c916123093f69e7f26d3778f1c7184b1f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976192"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject (Método)
Asigna una nueva instancia de objeto y llama al método de constructor especificado.  
  
 Este método está obsoleto en la .NET Framework versión 2,0. Use [ICorDebugEval2:: NewParameterizedObject (](icordebugeval2-newparameterizedobject-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pConstructor`  
 de Constructor al que se va a llamar.  
  
 `nArgs`  
 [in] Tamaño de la matriz `ppArgs`.  
  
 `ppArgs`  
 de Una matriz de objetos ICorDebugValue, cada uno de los cuales representa un argumento que se va a pasar al constructor.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también

- [Método NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)
