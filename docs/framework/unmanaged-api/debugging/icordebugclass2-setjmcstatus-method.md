---
title: "ICorDebugClass2::SetJMCStatus (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da9f61bd9a652b4c8e340ddecdee4b48bbdb086e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus (Método)
Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bIsJustMyCode`  
 [in] Establecido en `true` para indicar que el método es definido por el usuario de código; en caso contrario, establézcalo en `false`.  
  
## <a name="remarks"></a>Comentarios  
 Un paso a paso desencadene solo mi código ("JMC) omitirá el código no definido por el usuario. Código definido por el usuario debe ser un subconjunto del código depurable.  
  
 `SetJMCStatus`Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor de cualquier método, incluso si establece correctamente el valor de todos los demás métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
