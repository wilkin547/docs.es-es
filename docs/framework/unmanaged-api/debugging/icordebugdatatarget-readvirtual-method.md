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
ms.openlocfilehash: 36a18d92f05db55957bba55de84490c0da1a1f86
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976517"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual (Método)
Obtiene un bloque de memoria contigua que comienza en la dirección especificada y lo devuelve en el búfer proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 de Dirección de inicio de la memoria solicitada.  
  
 `pbuffer`  
 enuncia Búfer donde se almacenará la memoria.  
  
 `bytesRequested`  
 de Número de bytes que se van a obtener de la dirección de destino.  
  
 `pBytesRead`  
 enuncia Número de bytes realmente leídos de la dirección de destino. Puede ser menor que `bytesRequested`.  
  
## <a name="remarks"></a>Observaciones  
 Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver Success (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugDataTarget (Interfaz)](icordebugdatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
