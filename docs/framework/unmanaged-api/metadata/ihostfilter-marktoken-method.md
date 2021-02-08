---
description: 'Más información sobre: Ihostfilter (:: MarkToken ((método)'
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
ms.openlocfilehash: c8f5ecdef56b77e1b0031a93d6d8f7de79de4c3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784189"
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
  
## <a name="remarks"></a>Observaciones  

 Normalmente, desea que se procese un token si está en el ámbito de metadatos. El `MarkToken` método se pasa al motor de metadatos mediante el método [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IHostFilter (Interfaz)](ihostfilter-interface.md)
