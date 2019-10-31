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
ms.openlocfilehash: c084a3fcbbc02504124a511c6e136be32f408d21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112324"
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
  
## <a name="parameters"></a>Parámetros  
 `addr`  
 de `CLRDATA_ADDRESS` valor que especifica la dirección inicial de la memoria que se va a liberar.  
  
 `size`  
 de Tamaño, en bytes, de la memoria que se va a liberar.  
  
 `typeFlags`  
 de Marcas que controlan la liberación de memoria. Vea la función `VirtualFree` de Win32.  
  
## <a name="remarks"></a>Comentarios  
 El método `FreeVirtual` actúa como contenedor lógico para la función de `VirtualFree` de Win32.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [AllocVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
