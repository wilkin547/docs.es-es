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
ms.openlocfilehash: 205ad3af81fb6fabda5cbe291536f8858999f831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113701"
---
# <a name="iclrdatatargetgettlsvalue-method"></a>ICLRDataTarget::GetTLSValue (Método)
Obtiene un valor del almacenamiento local para el subproceso (TLS) del subproceso especificado en el proceso de destino. Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.  
  
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
 de Identificador del sistema operativo de un subproceso en el proceso de destino.  
  
 `index`  
 de Índice de la ubicación. Este valor debe ser un índice válido en el almacén local del subproceso especificado.  
  
 `value`  
 enuncia Un puntero a un valor de `CLRDATA_ADDRESS` que especifica el valor devuelto desde la ubicación TLS determinada.  
  
## <a name="remarks"></a>Comentarios  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
