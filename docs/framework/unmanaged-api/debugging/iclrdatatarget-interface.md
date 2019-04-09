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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100254"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget (Interfaz)
Proporciona métodos para la interacción con un elemento de destino de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCurrentThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Obtiene el identificador de sistema operativo para el subproceso actual.|  
|[Método GetImageBase](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Obtiene la dirección de memoria de base de la imagen especificada.|  
|[Método GetMachineType](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Obtiene un identificador para el tipo de conjunto de instrucciones que se está usando el proceso de destino.|  
|[Método GetPointerSize](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Obtiene el tamaño, en bytes, de un puntero al destino actual.|  
|[Método GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Obtiene un puntero al contexto del subproceso con el identificador especificado.|  
|[Método GetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.|  
|[Método ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Lee datos desde la dirección de memoria virtual especificada en el búfer especificado.|  
|[Método Request](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, como se define en la implementación.|  
|[Método SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Establece el contexto actual del subproceso especificado en el proceso de destino.|  
|[Método SetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.|  
|[Método WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.|  
  
## <a name="remarks"></a>Comentarios  
 El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
