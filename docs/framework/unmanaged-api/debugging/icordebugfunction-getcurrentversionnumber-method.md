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
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212912"
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
 enuncia Un puntero a un valor entero que es el número de versión de la edición más reciente realizada a esta función.  
  
## <a name="remarks"></a>Observaciones  
 El número de versión de la última edición realizada a esta función puede ser mayor que el número de versión de la propia función. Use el método [ICorDebugFunction2:: GetVersionNumber (](icordebugfunction2-getversionnumber-method.md) o el método [ICorDebugCode:: GetVersionNumber (](icordebugcode-getversionnumber-method.md) para recuperar el número de versión de la función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
