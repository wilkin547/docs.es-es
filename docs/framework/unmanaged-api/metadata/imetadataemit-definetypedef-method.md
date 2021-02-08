---
description: 'Más información acerca de: IMetaDataEmit::D método efineTypeDef'
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
ms.openlocfilehash: ca0c74b8c067771e9f45a8c00639d75c9ad08de1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784046"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef (Método)

Crea una definición de tipo para un Common Language Runtime tipo y obtiene un símbolo (token) de metadatos para esa definición de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Nombre del tipo en Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` sus. Se trata de una máscara de máscara de `CoreTypeAttr` valores.  
  
 `tkExtends`  
 de Token de la clase base. Debe ser un `mdTypeDef` o un `mdTypeRef` token.  
  
 `rtkImplements`  
 de Una matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.  
  
 `ptd`  
 enuncia El `mdTypeDef` token asignado.  
  
## <a name="remarks"></a>Observaciones  

 Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un tipo de referencia del sistema de tipos comunes (clase o interfaz) o un tipo de valor del sistema de tipos comunes.  
  
 Dependiendo de los parámetros proporcionados, este método, como efecto secundario, también puede crear un `mdInterfaceImpl` registro para cada interfaz heredada o implementada por este tipo. Sin embargo, este método no devuelve ninguno de estos `mdInterfaceImpl` tokens. Si un cliente desea agregar o modificar un token más tarde `mdInterfaceImpl` , debe usar la `IMetaDataImport` interfaz para enumerarlos. Si desea utilizar la semántica COM de la `[default]` interfaz, debe proporcionar la interfaz predeterminada como el primer elemento de `rtkImplements` ; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el primer `mdInterfaceImpl` token declarado para la clase).  
  
 Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` `mdTypeRef` token o. El último elemento de la matriz debe ser `mdTokenNil` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
