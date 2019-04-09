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
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084926"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum (Función)
Obtiene un puntero a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instancia que puede enumerar los objetos en el ensamblado con los valores especificados [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).  
  
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
  
## <a name="parameters"></a>Parámetros  
 `pEnum`  
 [out] Puntero a una ubicación de memoria que contiene la información solicitada `IAssemblyEnum` puntero.  
  
 `pUnkReserved`  
 [in] Reservado para extensibilidad futura. `pUnkReserved` debe ser una referencia nula.  
  
 `pName`  
 [in] El `IAssemblyName` del ensamblado solicitado. Este nombre se usa para filtrar la enumeración. Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.  
  
 `dwFlags`  
 [in] Marcas para modificar el comportamiento del enumerador. Este parámetro contiene exactamente un bit de la [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeración.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="remarks"></a>Comentarios  
 El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyEnum (Interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [IAssemblyName (Interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
