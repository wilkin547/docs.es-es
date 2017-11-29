---
title: "IMetaDataEmit::DefineNestedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineNestedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf0357275b0ad2dd7d57a3b3f07e17dc3e38e1a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType (Método)
Crea la firma de metadatos de una definición de tipo, se devuelve un `mdTypeDef` de token de ese tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szTypeDef`  
 [in] El nombre del tipo en Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` atributos. Se trata de una máscara de bits de `CorTypeAttr` valores.  
  
 `tkExtends`  
 [in] El token de la clase base. Esto es un `mdTypeDef` o un `mdTypeRef` símbolo (token).  
  
 `rtkImplements`[]  
 [in] Una matriz de símbolos (tokens) que especifican las interfaces que implementa esta interfaz o clase.  
  
 `tdEncloser`  
 [in] El token del tipo envolvente. El último elemento de la matriz debe ser `mdTokenNil`.  
  
 `ptd`  
 [out] El `mdTypeDef` token asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
