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
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175764"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef (Método)
Crea una definición de tipo para un tipo de Common Language Runtime y obtiene un token de metadatos para esa definición de tipo.  
  
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
 [en] El nombre del tipo en Unicode.  
  
 `dwTypeDefFlags`  
 [en] `TypeDef` atributos. Esta es una `CoreTypeAttr` máscara de bits de valores.  
  
 `tkExtends`  
 [en] El token de la clase base. Debe ser un `mdTypeDef` token `mdTypeRef` o un token.  
  
 `rtkImplements`  
 [en] Matriz de tokens que especifica las interfaces que implementa esta clase o interfaz.  
  
 `ptd`  
 [fuera] El `mdTypeDef` token asignado.  
  
## <a name="remarks"></a>Observaciones  
 Un indicador `dwTypeDefFlags` en especifica si el tipo que se está creando es un tipo de referencia de sistema de tipo común (clase o interfaz) o un tipo de valor de sistema de tipo común.  
  
 Dependiendo de los parámetros proporcionados, este método, `mdInterfaceImpl` como efecto secundario, también puede crear un registro para cada interfaz heredada o implementada por este tipo. Sin embargo, este método `mdInterfaceImpl` no devuelve ninguno de estos tokens. Si un cliente desea agregar `mdInterfaceImpl` o modificar posteriormente `IMetaDataImport` un token, debe usar la interfaz para enumerarlos. Si desea utilizar la semántica `[default]` COM de la interfaz, debe proporcionar `rtkImplements`la interfaz predeterminada como el primer elemento en ; un atributo personalizado establecido en la clase indicará que la clase tiene una `mdInterfaceImpl` interfaz predeterminada (que siempre se supone que es el primer token declarado para la clase).  
  
 Cada elemento `rtkImplements` de la `mdTypeDef` matriz `mdTypeRef` contiene un token o. El último elemento de `mdTokenNil`la matriz debe ser .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
