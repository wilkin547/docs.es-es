---
title: IMetaDataTables::GetGuidHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: 1b524067ac72dfd3bd19475f11d4ec12a307731d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702438"
---
# <a name="imetadatatablesgetguidheapsize-method"></a>IMetaDataTables::GetGuidHeapSize (Método)

Obtiene el tamaño, en bytes, del montón GUID.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pcbGuids`  
 enuncia Puntero al tamaño, en bytes, del montón GUID.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
