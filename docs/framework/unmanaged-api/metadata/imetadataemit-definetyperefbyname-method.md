---
description: 'Más información acerca de: IMetaDataEmit::D método efineTypeRefByName'
title: IMetaDataEmit::DefineTypeRefByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 836516e06105bb8ebc7c9bacf7b7d3837bf89eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784020"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName (Método)

Obtiene un símbolo (token) de metadatos para un tipo definido en el ámbito especificado, que está fuera del ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tkResolutionScope`  
 de El token que especifica el ámbito de resolución. Los siguientes tipos de token son válidos:  
  
- `mdModuleRef`, si el tipo está definido en el mismo ensamblado en el que se define el llamador.  
  
- `mdAssemblyRef`, si el tipo se define en un ensamblado distinto de aquél en el que se define el llamador.  
  
- `mdTypeRef`, si el tipo es un tipo anidado.  
  
- `mdModule`, si el tipo se define en el mismo módulo en el que se define el llamador.  
  
- Null, si el tipo está definido globalmente.  
  
 `szName`  
 de Nombre del tipo de destino en Unicode.  
  
 `ptr`  
 enuncia Puntero al `mdTypeRef` token que se asigna al tipo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
