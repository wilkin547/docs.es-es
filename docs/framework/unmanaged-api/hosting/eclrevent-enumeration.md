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
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131132"
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
|`Event_DomainUnload`|Especifica la descarga de un <xref:System.AppDomain>determinado.|  
|`Event_MDAFired`|Especifica que se ha generado un mensaje del Asistente para la depuración administrada (MDA).|  
|`Event_StackOverflow`|Especifica que se ha producido un error de desbordamiento de pila.|  
  
## <a name="remarks"></a>Comentarios  
 El host puede registrar devoluciones de llamada para cualquiera de los tipos de evento descritos por `EClrEvent` llamando a métodos de la interfaz [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) . El host obtiene un puntero a esta interfaz llamando al método [ICLRControl:: GetCLRManager (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .  
  
 Los eventos `Event_CLRDisabled` y `Event_DomainUnload` se pueden generar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
 El evento `Event_MDAFired` genera la creación de una instancia de [MDAInfo (](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) que contiene los detalles del mensaje de MDA. Para obtener más información acerca de los MDA, vea [diagnosticar errores con asistentes para la depuración administrada](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IActionOnCLREvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
