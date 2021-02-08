---
description: 'Más información sobre: IMetaDataEmit2:: SaveDeltaToMemory ((método)'
title: IMetaDataEmit2::SaveDeltaToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 3ef01889df6dede85947508ca08635c95d655666
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771761"
---
# <a name="imetadataemit2savedeltatomemory-method"></a>IMetaDataEmit2::SaveDeltaToMemory (Método)

Guarda los cambios de la sesión de edición y continuación actual en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbData`  
 enuncia Dirección en la que se va a comenzar a escribir la diferencia de metadatos.  
  
 `cbData`  
 de Tamaño de los cambios. Use [IMetaDataEmit2:: GetDeltaSaveSize (](imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
