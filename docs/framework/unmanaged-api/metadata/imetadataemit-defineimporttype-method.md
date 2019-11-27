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
ms.openlocfilehash: 5b4b0682b2bddff96cb3d720900ed3aa39f06f9d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431851"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType (Método)
Crea una referencia al tipo especificado que se define fuera del ámbito actual y define un token para esa referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `pAssemImport`  
 de Una interfaz [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el tipo de destino.  
  
 `pbHashValue`  
 de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport`.  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 de Interfaz [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el tipo de destino.  
  
 `tdImport`  
 de `mdTypeDef` token que especifica el tipo de destino.  
  
 `pAssemEmit`  
 de Una interfaz [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el tipo de destino.  
  
 `ptr`  
 enuncia El token de `mdTypeRef` que se define en el ámbito actual para la referencia de tipo.  
  
## <a name="remarks"></a>Comentarios  
 Antes de llamar al método [IMetaDataEmit::D efineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) , puede utilizar el método `DefineImportType` para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
