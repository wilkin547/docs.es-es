---
title: EClrEvent (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 5d6ec42da60a7b294177063b9f8bd5afbf352c62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726826"
---
# <a name="eclrevent-enumeration"></a>EClrEvent (Enumeración)

Describe los eventos de Common Language Runtime (CLR) para los que el host puede registrar devoluciones de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`Event_ClrDisabled`|Especifica un error grave de CLR.|  
|`Event_DomainUnload`|Especifica la descarga de un determinado <xref:System.AppDomain> .|  
|`Event_MDAFired`|Especifica que se ha generado un mensaje del Asistente para la depuración administrada (MDA).|  
|`Event_StackOverflow`|Especifica que se ha producido un error de desbordamiento de pila.|  
  
## <a name="remarks"></a>Comentarios  

 El host puede registrar devoluciones de llamada para cualquiera de los tipos de evento descritos por `EClrEvent` llamando a métodos de la interfaz [ICLROnEventManager](iclroneventmanager-interface.md) . El host obtiene un puntero a esta interfaz llamando al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .  
  
 Los `Event_CLRDisabled` `Event_DomainUnload` eventos y se pueden generar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
 El `Event_MDAFired` evento genera la creación de una instancia de [MDAInfo (](mdainfo-structure.md) que contiene los detalles del mensaje de MDA. Para obtener más información acerca de los MDA, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IActionOnCLREvent (Interfaz)](iactiononclrevent-interface.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
