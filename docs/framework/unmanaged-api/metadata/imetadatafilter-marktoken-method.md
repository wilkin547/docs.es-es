---
title: IMetaDataFilter::MarkToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
ms.openlocfilehash: ae105a60969e819f7974735ed8f075c60ba93916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440349"
---
# <a name="imetadatafiltermarktoken-method"></a>IMetaDataFilter::MarkToken (Método)
Establece un valor que indica que se ha procesado el token de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 de Token que se va a marcar como procesado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataFilter (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
