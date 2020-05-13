---
title: ICorDebugProcess::IsTransitionStub (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83211543"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub (Método)
Obtiene un valor que indica si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 de `CORDB_ADDRESS`Valor que especifica la dirección en cuestión.  
  
 `pbTransitionStub`  
 enuncia Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que producirá una transición a código administrado; de lo contrario, * `pbTransitionStub` es `false` .  
  
## <a name="remarks"></a>Observaciones  
 El `IsTransitionStub` código de paso no administrado puede utilizar el método para decidir cuándo devolver el control de versiones al stepper administrado.  
  
 También puede identificar los códigos auxiliares de transición examinando la información del archivo portable ejecutable (PE).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
