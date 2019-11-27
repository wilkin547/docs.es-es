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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450218"
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
 [in] atributos de `TypeDef`. Se trata de una máscara de máscara de valores `CoreTypeAttr`.  
  
 `tkExtends`  
 de Token de la clase base. Debe ser un `mdTypeDef` o un token de `mdTypeRef`.  
  
 `rtkImplements`  
 de Una matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.  
  
 `ptd`  
 enuncia El token de `mdTypeDef` asignado.  
  
## <a name="remarks"></a>Comentarios  
 Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un tipo de referencia del sistema de tipos comunes (clase o interfaz) o un tipo de valor del sistema de tipos común.  
  
 Dependiendo de los parámetros proporcionados, este método, como efecto secundario, también puede crear un registro de `mdInterfaceImpl` para cada interfaz heredada o implementada por este tipo. Sin embargo, este método no devuelve ninguno de estos tokens de `mdInterfaceImpl`. Si un cliente desea agregar o modificar más adelante un token de `mdInterfaceImpl`, debe usar la interfaz `IMetaDataImport` para enumerarlos. Si desea utilizar la semántica COM de la interfaz `[default]`, debe proporcionar la interfaz predeterminada como el primer elemento de `rtkImplements`; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el primer token `mdInterfaceImpl` declarado para la clase).  
  
 Cada elemento de la matriz `rtkImplements` contiene un token de `mdTypeDef` o `mdTypeRef`. El último elemento de la matriz se debe `mdTokenNil`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
