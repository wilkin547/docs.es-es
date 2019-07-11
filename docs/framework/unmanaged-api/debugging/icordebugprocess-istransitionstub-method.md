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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec29aa748c437199434fa1394e1a00c82154447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766877"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub (Método)
Obtiene un valor que indica si es una dirección dentro de un código auxiliar que provocará una transición a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que especifica la dirección en cuestión.  
  
 `pbTransitionStub`  
 [out] Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que provocará una transición a código administrado; en caso contrario *`pbTransitionStub` es `false`.  
  
## <a name="remarks"></a>Comentarios  
 El `IsTransitionStub` método puede utilizarse por código no administrado de ejecución paso a paso para decidir cuándo se debe devolver el control de ejecución paso a paso para el componente administrado.  
  
 También puede códigos auxiliares de transición de identidad echando un vistazo a la información en el archivo portable ejecutable (PE).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
