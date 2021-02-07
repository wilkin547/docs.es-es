---
description: 'Más información sobre: ICLRDataTarget2:: Allocvirtual ((método)'
title: ICLRDataTarget2::AllocVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: d81474e4067599178285b6fa876919298617919d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729346"
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual (Método)

Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para asignar memoria en el espacio de direcciones de este proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `addr`  
 de `CLRDATA_ADDRESS` Valor que especifica la dirección de inicio solicitada de la memoria que se va a asignar.  
  
 `size`  
 de Tamaño, en bytes, de la memoria que se va a asignar.  
  
 `typeFlags`  
 de Marcas que controlan la asignación de memoria. Vea la `VirtualAlloc` función Win32.  
  
 `protectFlags`  
 de Atributos de protección de la memoria asignada. Vea la `VirtualAlloc` función Win32.  
  
 `virt`  
 enuncia Un puntero a un `CLRDATA_ADDRESS` valor que especifica la dirección inicial real de la memoria asignada.  
  
## <a name="remarks"></a>Observaciones  

 El `AllocVirtual` método actúa como contenedor lógico de la función de Win32 `VirtualAlloc` .  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (Interfaz)](iclrdatatarget2-interface.md)
- [Método FreeVirtual](iclrdatatarget2-freevirtual-method.md)
