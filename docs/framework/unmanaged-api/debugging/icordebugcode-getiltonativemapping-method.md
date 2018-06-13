---
title: ICorDebugCode::GetILToNativeMapping (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411391"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping (Método)
Obtiene una matriz de instancias de "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos del lenguaje intermedio (MSIL) de Microsoft a los desplazamientos nativos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cMap`  
 [in] Tamaño de la matriz `map`.  
  
 `pcMap`  
 [out] Un puntero al número real de elementos devueltos en la `map` matriz.  
  
 `map`  
 [out] Una matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estructuras, cada uno de los cuales representa una asignación de un desplazamiento MSIL a un desplazamiento nativo.  
  
 No hay ningún orden de la matriz de elementos devueltos.  
  
## <a name="remarks"></a>Comentarios  
 El `GetILToNativeMapping` método devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa el código nativo que se compila a partir de código MSIL con el compilador just-in-time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugCode (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
