---
title: IAssemblyCache::CreateAssemblyCacheItem (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c45257a76127adf2bcf9ab356639d4754d151bf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430689"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>IAssemblyCache::CreateAssemblyCacheItem (Método)
Obtiene una referencia a una nueva [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwFlags`  
 [in] Marcadores definidos en Fusion.idl. Se admiten los siguientes valores:  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0 X 00000002)  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
 `ppAsmItem`  
 [out] El valor devuelto `IAssemblyCacheItem` puntero.  
  
 `pszAssemblyName`  
 [in, opcional] Separados por comas, sin formato canónico `name=value` pares.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IAssemblyCache (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [IAssemblyCacheItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
