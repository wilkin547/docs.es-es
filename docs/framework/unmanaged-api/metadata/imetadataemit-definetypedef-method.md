---
title: IMetaDataEmit::DefineTypeDef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b6f5881f289bed258191baf4f43264ea6ba35db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141809"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef (Método)
Crea una definición de tipo para un tipo de common language runtime y obtiene un token de metadatos para esa definición de tipo.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `szTypeDef`  
 [in] El nombre del tipo en formato Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` atributos. Se trata de una máscara de bits de `CoreTypeAttr` valores.  
  
 `tkExtends`  
 [in] El token de la clase base. Debe ser un `mdTypeDef` o un `mdTypeRef` token.  
  
 `rtkImplements`  
 [in] Una matriz de los tokens de especificación de las interfaces que implementa esta clase o interfaz.  
  
 `ptd`  
 [out] El `mdTypeDef` token asignado.  
  
## <a name="remarks"></a>Comentarios  
 Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un sistema tipo común tipo de referencia (clase o interfaz) o un tipo de valor de sistema de tipo común.  
  
 Dependiendo de los parámetros proporcionados, este método, como un efecto secundario, también puede crear una `mdInterfaceImpl` registros para cada interfaz que es heredado o implementada por este tipo. Sin embargo, este método no devuelve cualquiera de estos `mdInterfaceImpl` tokens. Si un cliente desea agregar más adelante o modificar un `mdInterfaceImpl` token, debe usar el `IMetaDataImport` interfaz para enumerarlas. Si desea usar la semántica de COM de la `[default]` interfaz, debe proporcionar la interfaz predeterminada como el primer elemento en `rtkImplements`; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el en primer lugar `mdInterfaceImpl` token declarado para la clase).  
  
 Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` o `mdTypeRef` token. El último elemento de la matriz debe ser `mdTokenNil`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
