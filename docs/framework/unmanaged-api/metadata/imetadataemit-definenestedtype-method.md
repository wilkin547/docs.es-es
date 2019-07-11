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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7676c83e8b231606896cb6d1224633b4fa15e725
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777558"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType (Método)
Crea la firma de metadatos de una definición de tipo, se devuelve un `mdTypeDef` para ese tipo de token y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.  
  
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
 [in] El nombre del tipo en formato Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` atributos. Se trata de una máscara de bits de `CorTypeAttr` valores.  
  
 `tkExtends`  
 [in] El token de la clase base. Puede ser un `mdTypeDef` o un `mdTypeRef` token.  
  
 `rtkImplements`[]  
 [in] Una matriz de los tokens que especifican las interfaces que implementa esta clase o interfaz.  
  
 `tdEncloser`  
 [in] El token del tipo envolvente. Debe ser el último elemento de la matriz `mdTokenNil`.  
  
 `ptd`  
 [out] El `mdTypeDef` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
