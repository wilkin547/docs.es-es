---
title: IAssemblyCache::InstallAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
ms.openlocfilehash: ec08c786992996ec6f44038ff3c1596cada88484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127080"
---
# <a name="iassemblycacheinstallassembly-method"></a>IAssemblyCache::InstallAssembly (Método)
Instala el ensamblado especificado en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwFlags`  
 de Marcas definidas en Fusion. idl. Se admiten los siguientes valores:  
  
- IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
- IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)  
  
 `pszManifestFilePath`  
 de Ruta de acceso al manifiesto del ensamblado que se va a instalar.  
  
 `pRefData`  
 de Estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) que contiene los datos de la instalación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyCache (interfaz)](iassemblycache-interface.md)
