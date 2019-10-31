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
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129470"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus (Método)
Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este ICorDebugModule2 en el valor especificado, excepto los de la matriz `pTokens`, que establece en el valor opuesto.  
  
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
 de Se establece en `true` si se va a depurar el código; de lo contrario, establézcalo en `false`.  
  
 `cTokens`  
 [in] Tamaño de la matriz `pTokens`.  
  
 `pTokens`  
 de Matriz de valores de `mdToken`, cada uno de los cuales hace referencia a un método que tendrá su estado JMC establecido en!`bIsJustMycode`.  
  
## <a name="remarks"></a>Comentarios  
 El estado de JMC de cada método que se especifica en el `pTokens` matriz se establece en el opuesto del valor de `bIsJustMycode`. El estado de todos los demás métodos de este módulo se establece en el valor `bIsJustMycode`.  
  
 El método `SetJMCStatus` borra todas las configuraciones de JMC anteriores de este módulo.  
  
 El método `SetJMCStatus` devuelve un HRESULT S_OK si todas las funciones se establecieron correctamente. Devuelve un valor HRESULT de CORDBG_E_FUNCTION_NOT_DEBUGGABLE si algunas funciones que están marcadas como `true` no se pueden depurar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
