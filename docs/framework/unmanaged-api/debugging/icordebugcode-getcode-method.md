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
ms.openlocfilehash: 20eac75a1f1d13b6a30267d56ff66024725e6f33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674780"
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
  
## <a name="parameters"></a>Parámetros  

 `startOffset`  
 de Desplazamiento del principio de la función.  
  
 `endOffset`  
 de Desplazamiento del final de la función.  
  
 `cBufferAlloc`  
 de Tamaño de la `buffer` matriz en la que se devolverá el código.  
  
 `buffer`  
 enuncia Matriz en la que se devolverá el código.  
  
 `pcBufferSize`  
 enuncia Número de bytes devueltos.  
  
## <a name="remarks"></a>Comentarios  

 Si el código de la función se ha dividido en varios fragmentos, se concatenan en orden de desplazamiento nativo creciente. Los límites de la instrucción no se comprueban.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también

- [Método GetCodeChunks](icordebugcode2-getcodechunks-method.md)
