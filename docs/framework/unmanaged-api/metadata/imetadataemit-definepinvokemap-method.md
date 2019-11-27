---
title: IMetaDataEmit::DefinePinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 9d4ea16a212ac5f0120d63510f07eaee69af739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431489"
---
# <a name="imetadataemitdefinepinvokemap-method"></a>IMetaDataEmit::DefinePinvokeMap (Método)
Establece las características de la firma PInvoke del método al que hace referencia el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 de Token del método de destino.  
  
 `dwMappingFlags`  
 de Marcas usadas por PInvoke para realizar la asignación.  
  
 `szImportName`  
 de Nombre del método de exportación de destino en un archivo DLL no administrado.  
  
 `mrImportDLL`  
 de El token para la DLL nativa de destino.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
