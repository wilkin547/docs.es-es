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
ms.openlocfilehash: 4bbc7ac7d87c6a5d36dc3432c603bb7d16d62c00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747424"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks (Método)
Obtiene los fragmentos de código de los que está compuesto este objeto de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
