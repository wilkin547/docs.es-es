---
title: IMetaDataEmit::DefineImportType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68e6f7599db55ed9429f159b380a8a9f8ae3f034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447491"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType (Método)
Crea una referencia al tipo especificado que se define fuera del ámbito actual y define un símbolo (token) para esa referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAssemImport`  
 [in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado desde el que se importa el tipo de destino.  
  
 `pbHashValue`  
 [in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 [in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el tipo de destino.  
  
 `tdImport`  
 [in] Un `mdTypeDef` símbolo (token) que especifica el tipo de destino.  
  
 `pAssemEmit`  
 [in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el tipo de destino.  
  
 `ptr`  
 [out] El `mdTypeRef` (token) que se define en el ámbito actual para la referencia de tipo.  
  
## <a name="remarks"></a>Comentarios  
 Antes de llamar a la [DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) método, puede usar el `DefineImportType` método para crear una referencia de tipo, en el ámbito actual, para el miembro de la clase primaria o interfaz primaria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
