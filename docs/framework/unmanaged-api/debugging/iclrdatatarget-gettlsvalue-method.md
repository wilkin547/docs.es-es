---
title: ICLRDataTarget::GetTLSValue (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7de415b998ef97e7500c289a1bca4402d203b152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738690"
---
# <a name="iclrdatatargetgettlsvalue-method"></a>ICLRDataTarget::GetTLSValue (Método)
Obtiene un valor desde el almacenamiento local de subproceso (TLS) del subproceso especificado en el proceso de destino. Este método llama a los servicios de acceso de datos de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `threadID`  
 [in] El identificador del sistema operativo de un subproceso del proceso de destino.  
  
 `index`  
 [in] El índice de la ubicación. Este valor debe ser un índice válido en el almacén local del subproceso especificado.  
  
 `value`  
 [out] Un puntero a un `CLRDATA_ADDRESS` valor que especifica el valor devuelto desde la ubicación especificada de TLS.  
  
## <a name="remarks"></a>Comentarios  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
