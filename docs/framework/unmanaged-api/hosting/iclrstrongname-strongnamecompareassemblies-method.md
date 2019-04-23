---
title: ICLRStrongName::StrongNameCompareAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d4b885b6968b800bc965a9be1ec6b795a42220
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140665"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies (Método)
Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszAssembly1`  
 [in] La ruta de acceso al primer ensamblado.  
  
 `wszAssembly2`  
 [in] La ruta de acceso al segundo ensamblado.  
  
 `pdwResult`  
 [out] Uno de los siguientes valores:  
  
-   `SN_CMP_DIFFERENT` (0): Especifica que los ensamblados contienen datos diferentes.  
  
-   `SN_CMP_IDENTICAL` (1): Especifica que los ensamblados son exactamente las mismas, incluidos sus firmas y la suma de comprobación.  
  
-   `SN_CMP_SIGONLY` (2): Especifica que los ensamblados se diferencian únicamente por la firma y la suma de comprobación.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Comentarios  
 La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.  
  
## <a name="see-also"></a>Vea también

- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
