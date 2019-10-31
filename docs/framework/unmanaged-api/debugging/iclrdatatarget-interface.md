---
title: ICLRDataTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113490"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget (Interfaz)
Proporciona métodos para la interacción con un elemento de destino del Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCurrentThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Obtiene el identificador del sistema operativo para el subproceso actual.|  
|[GetImageBase (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Obtiene la dirección de memoria base para la imagen especificada.|  
|[GetMachineType (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.|  
|[GetPointerSize (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Obtiene el tamaño, en bytes, de un puntero al destino actual.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Obtiene un puntero al contexto del subproceso con el identificador especificado.|  
|[GetTLSValue (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.|  
|[ReadVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Lee datos de la dirección de memoria virtual especificada en el búfer especificado.|  
|[Método de solicitud](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.|  
|[SetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Establece el contexto actual del subproceso especificado en el proceso de destino.|  
|[SetTLSValue (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.|  
|[WriteVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Escribe datos del búfer especificado en la dirección de memoria virtual especificada.|  
  
## <a name="remarks"></a>Comentarios  
 El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
