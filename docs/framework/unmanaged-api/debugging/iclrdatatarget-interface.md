---
title: ICLRDataTarget (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a40276b28f3d20428f0d7eb0556a762fdb56801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget (Interfaz)
Proporciona métodos para la interacción con un elemento de destino de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCurrentThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Obtiene el identificador de sistema operativo para el subproceso actual.|  
|[GetImageBase (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Obtiene la dirección de memoria de base de la imagen especificada.|  
|[GetMachineType (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.|  
|[GetPointerSize (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Obtiene el tamaño, en bytes, de un puntero al destino actual.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Obtiene un puntero al contexto del subproceso con el identificador especificado.|  
|[GetTLSValue (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.|  
|[ReadVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Lee datos de la dirección de memoria virtual especificada en el búfer especificado.|  
|[Request (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, tal como se define por la implementación.|  
|[SetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Establece el contexto actual del subproceso especificado en el proceso de destino.|  
|[SetTLSValue (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.|  
|[WriteVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.|  
  
## <a name="remarks"></a>Comentarios  
 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino concreto. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
