---
description: 'Más información acerca de: IMetaDataTables:: GetStringHeapSize ((método)'
title: IMetaDataTables::GetStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 0ec9f4e2768cc78163db67bc9099fc9cafae8c8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687784"
---
# <a name="imetadatatablesgetstringheapsize-method"></a>IMetaDataTables::GetStringHeapSize (Método)

Obtiene el tamaño, en bytes, del montón de cadenas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pcbStrings`  
 enuncia Puntero al tamaño, en bytes, del montón de cadenas.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
