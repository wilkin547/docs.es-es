---
title: ICorDebugCode::GetCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178998"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode (Método)
Obtiene todo el código para la función especificada, con formato de desensamblado. Este método ha quedado en desuso en la versión 2.0 de .NET Framework. Utilice [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `startOffset`  
 [en] Desplazamiento del principio de la función.  
  
 `endOffset`  
 [en] Desplazamiento del final de la función.  
  
 `cBufferAlloc`  
 [en] El tamaño `buffer` de la matriz en la que se devolverá el código.  
  
 `buffer`  
 [fuera] Matriz en la que se devolverá el código.  
  
 `pcBufferSize`  
 [fuera] El número de bytes devueltos.  
  
## <a name="remarks"></a>Observaciones  
 Si el código de la función se ha dividido en varios fragmentos, se concatenan en orden de desplazamiento nativo creciente. Los límites de instrucción no se comprueban.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Consulte también

- [Método GetCodeChunks](icordebugcode2-getcodechunks-method.md)
