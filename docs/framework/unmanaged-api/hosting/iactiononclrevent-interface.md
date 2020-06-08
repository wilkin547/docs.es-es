---
title: IActionOnCLREvent (Interfaz)
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504334"
---
# <a name="iactiononclrevent-interface"></a>IActionOnCLREvent (Interfaz)
Proporciona el método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método OnEvent](iactiononclrevent-onevent-method.md)|Realiza una devolución de llamada para un evento registrado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [EClrEvent (Enumeración)](eclrevent-enumeration.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
