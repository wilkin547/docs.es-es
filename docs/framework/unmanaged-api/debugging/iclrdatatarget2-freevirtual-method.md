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
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723654"
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
 de `CLRDATA_ADDRESS` Valor que especifica la dirección inicial de la memoria que se va a liberar.  
  
 `size`  
 de Tamaño, en bytes, de la memoria que se va a liberar.  
  
 `typeFlags`  
 de Marcas que controlan la liberación de memoria. Vea la `VirtualFree` función Win32.  
  
## <a name="remarks"></a>Comentarios  

 El `FreeVirtual` método actúa como contenedor lógico de la función de Win32 `VirtualFree` .  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataTarget2 (Interfaz)](iclrdatatarget2-interface.md)
- [Método AllocVirtual](iclrdatatarget2-allocvirtual-method.md)
