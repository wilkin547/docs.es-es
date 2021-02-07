---
description: 'Más información acerca de: Createassemblyenum ((función)'
title: CreateAssemblyEnum (Función)
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: 47177fcf0cd9e1b492fa89b9fb80c5cdaaced689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761148"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum (Función)

Obtiene un puntero a una instancia de [IAssemblyEnum](iassemblyenum-interface.md) que puede enumerar los objetos del ensamblado con la [IAssemblyName](iassemblyname-interface.md)especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parámetros  

 `pEnum`  
 enuncia Puntero a una ubicación de memoria que contiene el `IAssemblyEnum` puntero solicitado.  
  
 `pUnkReserved`  
 [in] Reservado para extensibilidad futura. `pUnkReserved` debe ser una referencia nula.  
  
 `pName`  
 de `IAssemblyName` Del ensamblado solicitado. Este nombre se utiliza para filtrar la enumeración. Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.  
  
 `dwFlags`  
 de Marcas para modificar el comportamiento del enumerador. Este parámetro contiene exactamente un bit de la enumeración [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="remarks"></a>Observaciones  

 El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyEnum (Interfaz)](iassemblyenum-interface.md)
- [IAssemblyName (Interfaz)](iassemblyname-interface.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
