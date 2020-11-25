---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713774"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>Método ICorDebugDataTarget2::GetSymbolProviderForImage

Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `imageBaseAddress`  
 de [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base de un módulo.  
  
 `ppSymProvider`  
 enuncia Puntero a la dirección de un objeto [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) .  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
