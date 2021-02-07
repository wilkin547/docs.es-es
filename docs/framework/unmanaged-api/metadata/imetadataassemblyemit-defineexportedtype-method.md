---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineExportedType'
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
ms.openlocfilehash: 0da1b1eb0880b0ba9df0ba9ad70b460163dffc39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671118"
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
 de Nombre del tipo que se va a exportar. En la versión 1,1 del Common Language Runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre dado en `TypeDef` para el tipo.  
  
 `tkImplementation`  
 de Token que especifica dónde se implementa el tipo exportado. Los valores válidos y sus significados asociados son:  
  
- `mdFile` El tipo se implementa en un archivo diferente dentro de este ensamblado.  
  
- `mdAssemblyRef` El tipo se implementa en un ensamblado diferente.  
  
- `mdExportedTYpe` El tipo está anidado dentro de otro tipo.  
  
- `mdFileNil` El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.  
  
 `tkTypeDef`  
 de Token a los metadatos que especifica el tipo que se va a exportar. Este valor se especifica en la `TypeDef` tabla del archivo que implementa el tipo y solo es relevante si ese archivo está en este ensamblado.  
  
 `dwExportedTypeFlags`  
 de Combinación bit a bit de los valores de enumeración de [cortypeattr (](cortypeattr-enumeration.md) que definen los valores de propiedad para el tipo exportado.  
  
 `pmdct`  
 enuncia Puntero al símbolo (token) de metadatos devuelto que indica el tipo exportado.  
  
## <a name="remarks"></a>Observaciones  

 `ExportedType`Se debe definir una estructura de metadatos para cada tipo expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
