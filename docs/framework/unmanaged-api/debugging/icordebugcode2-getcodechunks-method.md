---
title: ICorDebugCode2::GetCodeChunks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750155"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks (Método)
Obtiene los fragmentos de código de los que está compuesto este objeto de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbufSize`  
 [in] Tamaño de la `chunks` matriz.  
  
 `pcnumChunks`  
 [out] El número de fragmentos que se devuelven en el `chunks` matriz.  
  
 `chunks`  
 [out] Una matriz de estructuras "CodeChunkInfo", cada uno de los cuales representa un único fragmento de código. Si el valor de `cbufSize` es 0, este parámetro puede ser null.  
  
## <a name="remarks"></a>Comentarios  
 Los fragmentos de código nunca se superpondrán y siguen el orden en que habría concatenados [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md). Un objeto de código de lenguaje intermedio (MSIL) de Microsoft en la versión 2.0 de .NET Framework, perderá un único fragmento de código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
