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
ms.openlocfilehash: 7297bfa5297878dde6867a99029ac88754a05290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723589"
---
# <a name="iclrdatatarget3-interface"></a>ICLRDataTarget3 (Interfaz)

Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)|Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.|  
|[Método GetExceptionContextRecord](iclrdatatarget3-getexceptioncontextrecord-method.md)|Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.|  
|[Método GetExceptionThreadID](iclrdatatarget3-getexceptionthreadid-method.md)|Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.|  
  
## <a name="remarks"></a>Comentarios  

 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria. Puede que el destino no admita la modificación de sus áreas de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget (Interfaz)](iclrdatatarget-interface.md)
- [ICLRDataTarget2 (Interfaz)](iclrdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
