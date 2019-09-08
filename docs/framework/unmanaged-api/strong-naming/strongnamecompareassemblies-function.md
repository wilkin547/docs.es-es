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
ms.openlocfilehash: b0c2e8e46c7bb3a5e693c9ea16e6c5a0722b1898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799152"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies (Función)
Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameCompareAssemblies (](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) en su lugar.  
  
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
 de Ruta de acceso al primer ensamblado.  
  
 `wszAssembly2`  
 de Ruta de acceso al segundo ensamblado.  
  
 `pdwResult`  
 enuncia Uno de los siguientes valores:  
  
- `SN_CMP_DIFFERENT`(0): especifica que los ensamblados contienen datos diferentes.  
  
- `SN_CMP_IDENTICAL`(1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.  
  
- `SN_CMP_SIGONLY`(2): especifica que los ensamblados solo se diferencian en la firma y la suma de comprobación.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Comentarios  
 La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.  
  
 Si la `StrongNameCompareAssemblies` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="see-also"></a>Vea también

- [StrongNameCompareAssemblies (método)](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
