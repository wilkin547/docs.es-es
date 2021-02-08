---
description: 'Más información sobre: IMetaDataEmit2:: SaveDelta ((método)'
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
ms.openlocfilehash: 6e7a7527125869fea041f407da056db3eea88cbe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771774"
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
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
