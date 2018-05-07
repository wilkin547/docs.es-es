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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46532592057f4fa6d9883d46dcef2f8f9e5f7228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual (Método)
Llamado por los servicios de acceso a datos de common language runtime (CLR) para asignar memoria en el espacio de direcciones de este proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `addr`  
 [in] Un `CLRDATA_ADDRESS` valor que especifica la dirección inicial solicitada de la memoria que se va a asignar.  
  
 `size`  
 [in] El tamaño, en bytes, de la memoria que se va a asignar.  
  
 `typeFlags`  
 [in] Marcas que controlan la asignación de memoria. Vea el Win32 `VirtualAlloc` función.  
  
 `protectFlags`  
 [in] Los atributos de protección de la memoria asignada. Vea el Win32 `VirtualAlloc` función.  
  
 `virt`  
 [out] Un puntero a un `CLRDATA_ADDRESS` valor que especifica la dirección inicial real de la memoria asignada.  
  
## <a name="remarks"></a>Comentarios  
 El `AllocVirtual` método actúa como un contenedor lógico para Win32 `VirtualAlloc` función.  
  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [FreeVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
