---
title: ICorDebugFunction::GetCurrentVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be66e0e2c9aff788d1003878891b8d64d6353500
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754697"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>ICorDebugFunction::GetCurrentVersionNumber (Método)
Obtiene el número de versión de la edición más reciente realizada en la función representada por este objeto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnCurrentVersion`  
 [out] Un puntero a un valor entero que es el número de versión de la edición más reciente realizada en esta función.  
  
## <a name="remarks"></a>Comentarios  
 El número de versión de la edición más reciente realizada en esta función puede ser mayor que el número de versión de la propia función. Usar el [Icordebugfunction2](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) método o la [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método para recuperar el número de versión de la función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
