---
title: ICLRDataTarget3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: f7635dc3fad9b3de30fa052c7d2e67a7e6953fb3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789051"
---
# <a name="iclrdatatarget3-interface"></a>ICLRDataTarget3 (Interfaz)
Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetExceptionRecord (método)](iclrdatatarget3-getexceptionrecord-method.md)|Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.|  
|[GetExceptionContextRecord (método)](iclrdatatarget3-getexceptioncontextrecord-method.md)|Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.|  
|[GetExceptionThreadID (método)](iclrdatatarget3-getexceptionthreadid-method.md)|Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.|  
  
## <a name="remarks"></a>Notas  
 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria. Puede que el destino no admita la modificación de sus áreas de memoria.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
- [ICLRDataTarget2 (interfaz)](iclrdatatarget2-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
