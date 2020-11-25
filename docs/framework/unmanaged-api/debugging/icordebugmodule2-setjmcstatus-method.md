---
title: ICorDebugModule2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: cfa6df7a812559f05a4c57381a5007c9c90238e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709666"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus (Método)

Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este ICorDebugModule2 en el valor especificado, excepto los de la `pTokens` matriz, que se establece en el valor opuesto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `bIsJustMycode`  
 de Se establece en `true` si se va a depurar el código; de lo contrario, se establece en `false` .  
  
 `cTokens`  
 [in] Tamaño de la matriz `pTokens`.  
  
 `pTokens`  
 de Una matriz de `mdToken` valores, cada uno de los cuales hace referencia a un método que tendrá su estado JMC establecido en! `bIsJustMycode` .  
  
## <a name="remarks"></a>Comentarios  

 El estado de JMC de cada método que se especifica en la `pTokens` matriz se establece en el opuesto del `bIsJustMycode` valor. El estado de todos los demás métodos de este módulo se establece en el `bIsJustMycode` valor.  
  
 El `SetJMCStatus` método borra todas las configuraciones de JMC anteriores de este módulo.  
  
 El `SetJMCStatus` método devuelve un S_OK HRESULT si todas las funciones se establecieron correctamente. Devuelve un CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT si algunas funciones marcadas `true` no se pueden depurar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
