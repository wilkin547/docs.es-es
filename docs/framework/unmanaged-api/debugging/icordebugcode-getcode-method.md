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
ms.openlocfilehash: 14a72e4622aac09840e43f8bcdcf8a8c8d6e6892
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777912"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode (Método)
Obtiene todo el código para la función especificada, con formato de desensamblado. Este método está en desuso en la versión .NET Framework 2,0. Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.  
  
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
  
## <a name="parameters"></a>Parameters  
 `startOffset`  
 de Desplazamiento del principio de la función.  
  
 `endOffset`  
 de Desplazamiento del final de la función.  
  
 `cBufferAlloc`  
 de Tamaño de la matriz de `buffer` en la que se devolverá el código.  
  
 `buffer`  
 enuncia Matriz en la que se devolverá el código.  
  
 `pcBufferSize`  
 enuncia Número de bytes devueltos.  
  
## <a name="remarks"></a>Notas  
 Si el código de la función se ha dividido en varios fragmentos, se concatenan en orden de desplazamiento nativo creciente. Los límites de la instrucción no se comprueban.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Vea también

- [GetCodeChunks (método)](icordebugcode2-getcodechunks-method.md)
