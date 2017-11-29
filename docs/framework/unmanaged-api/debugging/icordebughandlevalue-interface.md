---
title: ICorDebugHandleValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue Interfaz1
Una subclase de ICorDebugReferenceValue que representa un valor de referencia a la que el depurador ha creado un identificador para la recolección.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dispose (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Libera el identificador hace referencia este `ICorDebugHandleValue` objeto sin liberar explícitamente el puntero de interfaz.|  
|[GetHandleType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Obtiene un valor de CorDebugHandleType que describe el tipo de identificador que hace referencia esta `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICorDebugReferenceValue` objeto se invalida mediante una interrupción en la ejecución del código depurado. Un `ICorDebugHandleValue` mantiene su referencia a través de interrupciones y continuaciones, hasta que se libere explícitamente.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
