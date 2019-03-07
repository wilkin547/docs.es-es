---
title: ICLRDataTarget::WriteVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1d9fdef9d183a03fd7f335a13683e1d1a3f95c8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485725"
---
# <a name="iclrdatatargetwritevirtual-method"></a>ICLRDataTarget::WriteVirtual (Método)
Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] CLRDATA_ADDRESS que almacena la dirección de memoria virtual.  
  
 `buffer`  
 [in] Un puntero a un búfer que almacena los datos que se va a escribir.  
  
 `bytesRequested`  
 [in] El número de bytes que se escribirán.  
  
 `bytesWritten`  
 [out] Un puntero al número real de bytes que se escribieron.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
