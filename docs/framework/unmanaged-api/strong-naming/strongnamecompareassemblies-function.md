---
title: StrongNameCompareAssemblies (Función)
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3693a42db8e32a4bb7a399f8c930da011130893
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778726"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies (Función)
Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
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
  
- `SN_CMP_DIFFERENT` (0): Especifica que los ensamblados contienen datos diferentes.  
  
- `SN_CMP_IDENTICAL` (1): Especifica que los ensamblados son exactamente las mismas, incluidos sus firmas y la suma de comprobación.  
  
- `SN_CMP_SIGONLY` (2): Especifica que los ensamblados se diferencian únicamente por la firma y la suma de comprobación.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Comentarios  
 La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.  
  
 Si el `StrongNameCompareAssemblies` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="see-also"></a>Vea también

- [StrongNameCompareAssemblies (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
