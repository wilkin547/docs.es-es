---
description: 'Más información sobre: IMetaDataEmit:: Merge (método)'
title: IMetaDataEmit::Merge (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 6b78dd20555acf1eaf610ed05d8a37ab6cdeee5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745949"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge (Método)

Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pImport`  
 de Un puntero a un objeto [IMetaDataImport](imetadataimport-interface.md) que identifica el ámbito importado que se va a combinar.  
  
 `pIMap`  
 de Un puntero a un objeto [IMapToken](imaptoken-interface.md) que especifica la reasignación del token.  
  
 `pHandler`  
 de Un puntero a un objeto [IUnknown](/cpp/atl/iunknown) que especifica los errores.  
  
## <a name="remarks"></a>Observaciones  

 Llame a [IMetaDataEmit:: mergeend (](imetadataemit-mergeend-method.md) para desencadenar la fusión de metadatos en un solo ámbito.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
