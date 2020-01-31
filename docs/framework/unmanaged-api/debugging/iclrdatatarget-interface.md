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
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793713"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget (Interfaz)
Proporciona métodos para la interacción con un elemento de destino del Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCurrentThreadID (método)](iclrdatatarget-getcurrentthreadid-method.md)|Obtiene el identificador del sistema operativo para el subproceso actual.|  
|[GetImageBase (método)](iclrdatatarget-getimagebase-method.md)|Obtiene la dirección de memoria base para la imagen especificada.|  
|[GetMachineType (método)](iclrdatatarget-getmachinetype-method.md)|Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.|  
|[GetPointerSize (método)](iclrdatatarget-getpointersize-method.md)|Obtiene el tamaño, en bytes, de un puntero al destino actual.|  
|[GetThreadContext (método)](iclrdatatarget-getthreadcontext-method.md)|Obtiene un puntero al contexto del subproceso con el identificador especificado.|  
|[GetTLSValue (método)](iclrdatatarget-gettlsvalue-method.md)|Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.|  
|[ReadVirtual (método)](iclrdatatarget-readvirtual-method.md)|Lee datos de la dirección de memoria virtual especificada en el búfer especificado.|  
|[Método de solicitud](iclrdatatarget-request-method.md)|Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.|  
|[SetThreadContext (método)](iclrdatatarget-setthreadcontext-method.md)|Establece el contexto actual del subproceso especificado en el proceso de destino.|  
|[SetTLSValue (método)](iclrdatatarget-settlsvalue-method.md)|Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.|  
|[WriteVirtual (método)](iclrdatatarget-writevirtual-method.md)|Escribe datos del búfer especificado en la dirección de memoria virtual especificada.|  
  
## <a name="remarks"></a>Notas  
 El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (interfaz)](iclrdatatarget2-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
