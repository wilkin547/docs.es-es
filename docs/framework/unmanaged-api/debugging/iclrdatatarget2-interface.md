---
title: ICLRDataTarget2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: dee5108439610b67c3397cebcd8ee5f84d4eacea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723641"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2 (Interfaz)

Una subclase de [ICLRDataTarget](iclrdatatarget-interface.md) utilizada por el nivel de servicios de acceso a datos para manipular regiones de memoria virtual en el proceso de destino.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AllocVirtual](iclrdatatarget2-allocvirtual-method.md)|Asigna memoria en el espacio de direcciones del proceso de destino.|  
|[Método FreeVirtual](iclrdatatarget2-freevirtual-method.md)|Libera memoria previamente asignada en el espacio de direcciones del proceso de destino.|  
  
## <a name="remarks"></a>Comentarios  

 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria. Puede que el destino no admita la modificación de sus áreas de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget (Interfaz)](iclrdatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
