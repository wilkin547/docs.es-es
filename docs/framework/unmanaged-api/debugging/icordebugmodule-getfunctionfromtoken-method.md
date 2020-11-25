---
title: ICorDebugModule::GetFunctionFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: bf2acd897c9c45e445b864f85550ed7ed6e00886
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710160"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken (Método)

Obtiene la función especificada por el token de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `methodDef`  
 de `mdMethodDef` Token de metadatos que hace referencia a los metadatos de la función.  
  
 `ppFunction`  
 enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFunction que representa la función.  
  
## <a name="remarks"></a>Comentarios  

 El `GetFunctionFromToken` método devuelve un CORDBG_E_FUNCTION_NOT_IL HRESULT si el valor pasado `methodDef` no hace referencia a un método de lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
