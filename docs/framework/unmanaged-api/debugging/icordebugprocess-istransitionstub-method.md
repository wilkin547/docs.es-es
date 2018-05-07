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
ms.openlocfilehash: e06dc35998a2874ed1d2f76725078874817e94d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub (Método)
Obtiene un valor que indica si una dirección está dentro de un código auxiliar que provocará una transición a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` valor que especifica la dirección en cuestión.  
  
 `pbTransitionStub`  
 [out] Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que provocará una transición a código administrado; en caso contrario *`pbTransitionStub` es `false`.  
  
## <a name="remarks"></a>Comentarios  
 El `IsTransitionStub` método se puede utilizar código no administrado de ejecución paso a paso para decidir cuándo se debe devolver el control de ejecución paso a paso para el paso a paso desencadene administrado.  
  
 También puede códigos auxiliares de transición de identidad examinando la información en el archivo ejecutable portable (PE).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
