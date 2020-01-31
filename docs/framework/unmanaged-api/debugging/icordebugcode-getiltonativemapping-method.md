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
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777890"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping (Método)
Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan las asignaciones de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `cMap`  
 [in] Tamaño de la matriz `map`.  
  
 `pcMap`  
 enuncia Puntero al número real de elementos devueltos en la matriz de `map`.  
  
 `map`  
 enuncia Matriz de estructuras de `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales representa una asignación de un desplazamiento de MSIL a un desplazamiento nativo.  
  
 No hay ningún orden en la matriz de elementos devueltos.  
  
## <a name="remarks"></a>Notas  
 El método `GetILToNativeMapping` devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa código nativo que se compiló Just-in-Time (JIT) a partir del código MSIL.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode (interfaz)](icordebugcode-interface1.md)
