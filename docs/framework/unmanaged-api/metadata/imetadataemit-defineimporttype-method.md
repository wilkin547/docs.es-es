---
description: 'Más información acerca de: IMetaDataEmit::D método efineImportType'
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
ms.openlocfilehash: 7afe0fe400e4eb6e177a06e00b2d69202820804c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753437"
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
 de Una interfaz [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el tipo de destino.  
  
 `pbHashValue`  
 de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport` .  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 de Interfaz [IMetaDataImport](imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el tipo de destino.  
  
 `tdImport`  
 de `mdTypeDef` Token que especifica el tipo de destino.  
  
 `pAssemEmit`  
 de Una interfaz [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el tipo de destino.  
  
 `ptr`  
 enuncia El `mdTypeRef` token que se define en el ámbito actual para la referencia de tipo.  
  
## <a name="remarks"></a>Observaciones  

 Antes de llamar al método [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) , puede utilizar el `DefineImportType` método para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
