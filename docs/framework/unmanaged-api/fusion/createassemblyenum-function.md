---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2098d5d9ce1c01f232cf2904c1fd3e990dfbe2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432121"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum (Función)
Obtiene un puntero a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instancia que puede enumerar los objetos incluidos en el ensamblado con los valores especificados [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pEnum`  
 [out] Puntero a una ubicación de memoria que contiene solicitado `IAssemblyEnum` puntero.  
  
 `pUnkReserved`  
 [in] Reservado para extensibilidad futura. `pUnkReserved` debe ser una referencia nula.  
  
 `pName`  
 [in] El `IAssemblyName` del ensamblado solicitado. Este nombre se utiliza para filtrar la enumeración. Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.  
  
 `dwFlags`  
 [in] Marcadores para modificar el comportamiento del enumerador. Este parámetro contiene exactamente un bit de la [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeración.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="remarks"></a>Comentarios  
 El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
