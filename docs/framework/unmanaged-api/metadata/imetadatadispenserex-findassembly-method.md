---
title: IMetaDataDispenserEx::FindAssembly (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713397"
---
# <a name="imetadatadispenserexfindassembly-method"></a>IMetaDataDispenserEx::FindAssembly (Método)

Este método no se implementa. Si se llama, devuelve E_NOTIMPL.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szAppBase`  
 [in] No se utiliza.  
  
 `szPrivateBin`  
 [in] No se utiliza.  
  
 `szGlobalBin`  
 [in] No se utiliza.  
  
 `szAssemblyName`  
 de Ensamblado que se va a buscar.  
  
 `szName`  
 enuncia Nombre simple del ensamblado.  
  
 `cchName`  
 de Tamaño, en bytes, de `szName` .  
  
 `pcName`  
 enuncia Número de caracteres devueltos realmente en `szName` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
