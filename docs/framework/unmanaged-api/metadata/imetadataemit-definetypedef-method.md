---
title: "IMetaDataEmit::DefineTypeDef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeDef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a344f592b47d452b4d016f08cefddda650128188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef (Método)
Crea una definición de tipo para un tipo de common language runtime y obtiene un símbolo (token) de metadatos para dicha definición de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szTypeDef`  
 [in] El nombre del tipo en Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` atributos. Se trata de una máscara de bits de `CoreTypeAttr` valores.  
  
 `tkExtends`  
 [in] El token de la clase base. Debe ser un `mdTypeDef` o un `mdTypeRef` símbolo (token).  
  
 `rtkImplements`  
 [in] Una matriz de símbolos (tokens) especifican las interfaces que implementa esta interfaz o clase.  
  
 `ptd`  
 [out] El `mdTypeDef` token asignado.  
  
## <a name="remarks"></a>Comentarios  
 Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un sistema tipo común tipo de referencia (clase o interfaz) o un tipo de valor de sistema de tipo común.  
  
 Dependiendo de los parámetros proporcionados, este método, como un efecto secundario, puede crear una `mdInterfaceImpl` registros para cada interfaz que es heredado o implementada por este tipo. Sin embargo, este método no devuelve cualquiera de estos `mdInterfaceImpl` símbolos (tokens). Si un cliente desea agregar más adelante o modificar un `mdInterfaceImpl` token, debe usar el `IMetaDataImport` interfaz para enumerarlas. Si desea usar la semántica de COM de la `[default]` interfaz, también debe proporcionar la interfaz predeterminada como el primer elemento en `rtkImplements`; un atributo personalizado que se establecen en la clase se indicará que la clase tiene una interfaz predeterminada (siempre que se supone que es el en primer lugar `mdInterfaceImpl` declarado de símbolo (token) de la clase).  
  
 Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` o `mdTypeRef` símbolo (token). El último elemento de la matriz debe ser `mdTokenNil`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
