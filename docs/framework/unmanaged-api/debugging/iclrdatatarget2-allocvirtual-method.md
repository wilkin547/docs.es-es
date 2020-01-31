---
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
ms.openlocfilehash: 51c06a7f8ea22fc73236131954781d8755274041
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789084"
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
  
## <a name="parameters"></a>Parameters  
 `addr`  
 de `CLRDATA_ADDRESS` valor que especifica la dirección de inicio solicitada de la memoria que se va a asignar.  
  
 `size`  
 de Tamaño, en bytes, de la memoria que se va a asignar.  
  
 `typeFlags`  
 de Marcas que controlan la asignación de memoria. Vea la función `VirtualAlloc` de Win32.  
  
 `protectFlags`  
 de Atributos de protección de la memoria asignada. Vea la función `VirtualAlloc` de Win32.  
  
 `virt`  
 enuncia Un puntero a un valor de `CLRDATA_ADDRESS` que especifica la dirección inicial real de la memoria asignada.  
  
## <a name="remarks"></a>Notas  
 El método `AllocVirtual` actúa como contenedor lógico para la función de `VirtualAlloc` de Win32.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (interfaz)](iclrdatatarget2-interface.md)
- [FreeVirtual (método)](iclrdatatarget2-freevirtual-method.md)
