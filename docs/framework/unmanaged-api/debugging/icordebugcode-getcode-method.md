---
title: "ICorDebugCode::GetCode (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12820d0be725c92754640aaa4eebca56bbc33ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode (Método)
Obtiene todo el código para la función especificada, con formato de desensamblado. Este método está en desuso en la versión 2.0 de .NET Framework. Use [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `startOffset`  
 [in] El desplazamiento del principio de la función.  
  
 `endOffset`  
 [in] El desplazamiento del final de la función.  
  
 `cBufferAlloc`  
 [in] El tamaño de la `buffer` de matriz en la que se devolverá el código.  
  
 `buffer`  
 [out] La matriz en la que se devolverá el código.  
  
 `pcBufferSize`  
 [out] Devuelve el número de bytes.  
  
## <a name="remarks"></a>Comentarios  
 Si el código de la función se ha dividido en varios fragmentos, se concatenan en orden creciente de desplazamiento nativo. No se comprueban los límites de instrucción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también  
 [GetCodeChunks (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
