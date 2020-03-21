---
title: IMetaDataAssemblyEmit::DefineExportedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177875"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType (Método)
Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szName`  
 [en] El nombre del tipo que se va a exportar. Para la versión 1.1 de Common Language Runtime, el nombre del `TypeDef` tipo exportado debe coincidir exactamente con el nombre especificado en el para el tipo.  
  
 `tkImplementation`  
 [en] Un token que especifica dónde se implementa el tipo exportado. Los valores válidos y sus significados asociados son:  
  
- `mdFile`El tipo se implementa en un archivo diferente dentro de este ensamblado.  
  
- `mdAssemblyRef`El tipo se implementa en un ensamblado diferente.  
  
- `mdExportedTYpe`El tipo está anidado dentro de algún otro tipo.  
  
- `mdFileNil`El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.  
  
 `tkTypeDef`  
 [en] Un token para los metadatos que especifica el tipo que se va a exportar. Este valor se `TypeDef` introduce en la tabla del archivo que implementa el tipo y sólo es relevante si ese archivo está en este ensamblado.  
  
 `dwExportedTypeFlags`  
 [en] Combinación bit a bit de valores de enumeración [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) que definen la configuración de propiedad para el tipo exportado.  
  
 `pmdct`  
 [fuera] Puntero al token de metadatos devuelto que indica el tipo exportado.  
  
## <a name="remarks"></a>Observaciones  
 Se `ExportedType` debe definir una estructura de metadatos para cada tipo expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
