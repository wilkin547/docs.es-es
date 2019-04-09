---
title: ICorDebugDataTarget::ReadVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111532"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual (Método)
Obtiene un bloque de memoria contigua a partir de la dirección especificada y lo devuelve en el búfer proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] La dirección de inicio de la memoria solicitada.  
  
 `pbuffer`  
 [out] El búfer donde se almacenará la memoria.  
  
 `bytesRequested`  
 [in] El número de bytes que se obtenga de la dirección de destino.  
  
 `pBytesRead`  
 [out] El número de bytes leídos realmente en la dirección de destino. Esto puede ser menor que `bytesRequested`.  
  
## <a name="remarks"></a>Comentarios  
 Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver correctamente (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
