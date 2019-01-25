---
title: ICorDebugEval::CallFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493b4850436b3724287210878992d1d8ce8fe168
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589404"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction (Método)
Configura una llamada a la función especificada.  
  
 Este método está obsoleto en .NET Framework versión 2.0. Use [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pFunction`  
 [in] Puntero a un objeto ICorDebugFunction que especifica la función debe llamarse.  
  
 `nArgs`  
 [in] El número de argumentos de la función.  
  
 `ppArgs`  
 [in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se pasará a la función.  
  
## <a name="remarks"></a>Comentarios  
 Si la función es virtual, `CallFunction` llevará a cabo distribución virtual. Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos son también en ese dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** WindowSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también
- [CallParameterizedFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
