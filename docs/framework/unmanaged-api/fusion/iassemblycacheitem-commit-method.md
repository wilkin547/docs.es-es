---
title: IAssemblyCacheItem::Commit (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b39cdec6d5cc10256c2911c98f94b7565295408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538003"
---
# <a name="iassemblycacheitemcommit-method"></a>IAssemblyCacheItem::Commit (Método)
Confirma la referencia de ensamblado en la caché en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwFlags`  
 [in] Marcadores definidos en Fusion.idl.  
  
 `pulDisposition`  
 [out, optional] Un valor que indica el resultado de la operación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IAssemblyCacheItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
