---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: GetIndex (método)'
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: f3a51c5ed5edacc9678c965ac385d0969e2ee8a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801116"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>ICorDebugMergedAssemblyRecord::GetIndex (método)

Obtiene el índice de prefijo del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pIndex`  
 [out] Puntero al índice de prefijo.  
  
## <a name="remarks"></a>Observaciones  

 El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
