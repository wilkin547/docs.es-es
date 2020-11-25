---
title: IMetaDataError::OnError (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 6f6e531c99d341eba39939a184d2424256d9e155
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701879"
---
# <a name="imetadataerroronerror-method"></a>IMetaDataError::OnError (Método)

Proporciona una notificación de los errores que se producen durante la combinación de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hrError`  
 de El valor de error HRESULT devuelto al método de llamada.  
  
 `token`  
 de Token de metadatos del objeto de código que se estaba combinando cuando se produjo el error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataError (Interfaz)](imetadataerror-interface.md)
