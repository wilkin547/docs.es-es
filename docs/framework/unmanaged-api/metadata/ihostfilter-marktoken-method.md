---
title: IHostFilter::MarkToken (Método)
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718233"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken (Método)

Indica que se procesará el token de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tk`  
 de Token de metadatos que se va a procesar.  
  
## <a name="remarks"></a>Comentarios  

 Normalmente, desea que se procese un token si está en el ámbito de metadatos. El `MarkToken` método se pasa al motor de metadatos mediante el método [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IHostFilter (Interfaz)](ihostfilter-interface.md)
