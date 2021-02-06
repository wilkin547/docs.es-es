---
description: 'Más información sobre: ICorDebugMutableDataTarget:: WriteVirtual ((método)'
title: ICorDebugMutableDataTarget::WriteVirtual (método)
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 3f3400456b7af51f4b24d7e14e35d641f03a8bfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637825"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a>ICorDebugMutableDataTarget::WriteVirtual (método)

Escribe la memoria en el espacio de direcciones de procesos de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a>Parámetros  

 `address`  
 [in] Dirección a la que se va a escribir el contenido de `pBuffer`.  
  
 `pBuffer`  
 [in] Puntero a una matriz de bytes que contiene los bytes que se van a escribir.  
  
 `address`  
 [in] Número de bytes en `pBuffer`.  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK`, si la operación se realiza correctamente o cualquier otro `HRESULT`, en caso de error.  
  
## <a name="remarks"></a>Observaciones  

 Si no se puede escribir bytes, la llamada al método produce un error sin cambiar los bytes en el espacio de la dirección de destino (de lo contrario, el destino estaría en un estado incoherente que haría que las futuras depuraciones resultasen poco fiables).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
