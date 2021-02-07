---
description: 'Más información acerca de: IMetaDataEmit::D método efineNestedType'
title: IMetaDataEmit::DefineNestedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 1b0c5c8d1bffa425b2019a4434042c84a0069907
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753385"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType (Método)

Crea la firma de metadatos de una definición de tipo, devuelve un `mdTypeDef` token para ese tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szTypeDef`  
 de Nombre del tipo en Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` sus. Se trata de una máscara de máscara de `CorTypeAttr` valores.  
  
 `tkExtends`  
 de Token de la clase base. Este es un `mdTypeDef` `mdTypeRef` token o.  
  
 `rtkImplements`[]  
 de Matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.  
  
 `tdEncloser`  
 de Token del tipo envolvente. El último elemento de la matriz debe ser `mdTokenNil` .  
  
 `ptd`  
 enuncia El `mdTypeDef` token asignado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
