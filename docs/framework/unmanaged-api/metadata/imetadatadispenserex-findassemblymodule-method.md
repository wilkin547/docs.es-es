---
description: 'Más información sobre: IMetaDataDispenserEx:: Findassemblymodule ((método)'
title: IMetaDataDispenserEx::FindAssemblyModule (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
ms.openlocfilehash: 39ea13a2d8f2436e86db513aaa33f990f43d8132
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753580"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a>IMetaDataDispenserEx::FindAssemblyModule (Método)

Este método no se implementa. Si se llama, devuelve E_NOTIMPL.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
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
 de Nombre del módulo.  
  
 `szModuleName`  
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
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
