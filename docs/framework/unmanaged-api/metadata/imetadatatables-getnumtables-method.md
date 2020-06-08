---
title: IMetaDataTables::GetNumTables (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: df02def0c14beb4e9ffd1b9260002767586a59b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490203"
---
# <a name="imetadatatablesgetnumtables-method"></a>IMetaDataTables::GetNumTables (Método)
Obtiene el número de tablas en el ámbito de la `IMetaDataTables` instancia actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pcTables`  
 enuncia Puntero al número de tablas en el ámbito de la instancia actual.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
