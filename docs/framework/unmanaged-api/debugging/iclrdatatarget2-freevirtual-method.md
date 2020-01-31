---
title: ICLRDataTarget2::FreeVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 7eda9bfff6de6b386c16ad0a188931d9d3adcb93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793660"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual (Método)
Lo llaman los servicios de acceso a datos de Common Language Runtime (CLR) para liberar memoria que se asignó previamente en el espacio de direcciones del proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `addr`  
 de `CLRDATA_ADDRESS` valor que especifica la dirección inicial de la memoria que se va a liberar.  
  
 `size`  
 de Tamaño, en bytes, de la memoria que se va a liberar.  
  
 `typeFlags`  
 de Marcas que controlan la liberación de memoria. Vea la función `VirtualFree` de Win32.  
  
## <a name="remarks"></a>Notas  
 El método `FreeVirtual` actúa como contenedor lógico para la función de `VirtualFree` de Win32.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (interfaz)](iclrdatatarget2-interface.md)
- [AllocVirtual (método)](iclrdatatarget2-allocvirtual-method.md)
