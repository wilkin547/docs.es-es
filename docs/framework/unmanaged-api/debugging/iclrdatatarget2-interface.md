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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc26694bded2c7df1a53a96e8743f3be73c93eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2 (Interfaz)
Una subclase de [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) que se usa la capa de servicios de acceso a datos para manipular las áreas de memoria virtual en el proceso de destino.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AllocVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|Asigna memoria en el espacio de direcciones del proceso de destino.|  
|[FreeVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|Libera memoria previamente asignada en el espacio de direcciones del proceso de destino.|  
  
## <a name="remarks"></a>Comentarios  
 El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto. Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria. Puede que el destino no admita la modificación de sus áreas de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
