---
title: IMetaDataAssemblyImport::GetExportedTypeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008409"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps (Método)
Obtiene el conjunto de propiedades del tipo exportado con la firma de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mdct`  
 de `mdExportedType`Token de metadatos que representa el tipo exportado.  
  
 `szName`  
 enuncia Nombre del tipo exportado.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName` .  
  
 `pchName`  
 enuncia Número de caracteres anchos realmente devueltos en`szName`  
  
 `ptkImplementation`  
 enuncia Un `mdFile` `mdAssemblyRef` `mdExportedType` token de metadatos, o que contiene o permite el acceso a las propiedades del tipo exportado.  
  
 `ptkTypeDef`  
 enuncia Un puntero a un `mdTypeDef` token que representa un tipo en el archivo.  
  
 `pdwExportedTypeFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados al tipo exportado. El valor de flags puede ser uno o varios valores de [cortypeattr (](cortypeattr-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
