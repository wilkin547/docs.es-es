---
title: IMetaDataEmit2::DefineGenericParam (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de8547ed0ee83bafe4612bdcd62607fc94fb3f69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163727"
---
# <a name="imetadataemit2definegenericparam-method"></a>IMetaDataEmit2::DefineGenericParam (Método)
Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 [in] Un `mdTypeDef` o `mdMethodDef` token que representa el método o constructor que se va a definir un parámetro genérico.  
  
 `ulParamSeq`  
 [in] El índice del parámetro genérico.  
  
 `dwParamFlags`  
 [in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.  
  
 `szname`  
 [in] El nombre del parámetro.  
  
 `reserved`  
 [in] Este parámetro está reservado para extensibilidad futura.  
  
 `rtkConstraints`  
 [in] Una matriz terminada en cero de restricciones de tipo. Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.  
  
 `pgp`  
 [out] Un token que representa el parámetro genérico.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
