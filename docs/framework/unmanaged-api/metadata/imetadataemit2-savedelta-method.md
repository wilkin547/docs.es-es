---
title: IMetaDataEmit2::SaveDelta (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: d3e25f271fc434785e25e7b226ad98f86b5f8dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492790"
---
# <a name="imetadataemit2savedelta-method"></a>IMetaDataEmit2::SaveDelta (Método)
Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szFile`  
 de Nombre del archivo en el que se van a guardar los cambios.  
  
 `dwSaveFlags`  
 [in] Reservado. Debe ser cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
