---
title: ICorDebugReferenceValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac6260a601f7fdacf84034a6ae83c9423fafa11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalue-interface1"></a>ICorDebugReferenceValue Interfaz1
Proporciona métodos que administran un valor que es una referencia a un objeto. (Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dereference (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Obtiene el objeto al que hace referencia.|  
|[DereferenceStrong (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Sin implementar. No llame a este método.|  
|[GetValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Obtiene la dirección de memoria actual del objeto de referencia.|  
|[IsNull (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no señala a un objeto.|  
|[SetValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Establece la dirección de memoria actual. Es decir, este método establece este `ICorDebugReferenceValue` para que apunte a un objeto.|  
  
## <a name="remarks"></a>Comentarios  
 Common language runtime (CLR) puede hacer una colección de elementos no utilizados en objetos cuando continúa el proceso depurado. La colección de elementos no utilizados puede mover objetos en la memoria. Un `ICorDebugReferenceValue` en cooperación con la recolección de elementos para que su información se actualiza después de la recolección de elementos no utilizados o quedarán invalidado implícitamente antes de la recolección de elementos.  
  
 La `ICorDebugReferenceValue` objeto puede invalidar implícitamente después de que se ha continuado el proceso depurado. No se invalida la derivada "ICorDebugHandleValue" hasta que se publican o se exponen explícitamente.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
    
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
