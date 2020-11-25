---
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
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719546"
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
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
