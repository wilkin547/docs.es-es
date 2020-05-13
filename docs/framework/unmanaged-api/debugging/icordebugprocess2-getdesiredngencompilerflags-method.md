---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213002"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
Obtiene la configuración actual del marcador de compilador que el Common Language Runtime (CLR) utiliza para seleccionar la imagen precompilada correcta (es decir, nativa) que se va a cargar en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwFlags`  
 enuncia Un puntero a una combinación bit a bit de los valores de enumeración de [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que se usan para seleccionar la imagen precompilada correcta que se va a cargar.  
  
## <a name="remarks"></a>Observaciones  
 Use el método [ICorDebugProcess2:: SetDesiredNGENCompilerFlags (](icordebugprocess2-setdesiredngencompilerflags-method.md) para establecer las marcas que CLR usará para seleccionar la imagen precompilada correcta que se va a cargar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
