---
title: StrongNameSignatureVerification (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129233"
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification (Función)
Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamesignatureverification (](../hosting/iclrstrongname-strongnamesignatureverification-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso al archivo portable ejecutable (. dll o. exe) para que lo compruebe el ensamblado.  
  
 `dwInFlags`  
 de Marcas para modificar el comportamiento de la comprobación. Se admiten los siguientes valores:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.  
  
- `SN_INFLAG_INSTALL` (0x00000002): especifica que es la primera vez que se comprueba el manifiesto.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado solo será accesible para el usuario actual.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.  
  
- `SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.  
  
 `pdwOutFlags`  
 enuncia Marcas que indican si se ha comprobado la firma de nombre seguro. Se admite el siguiente valor:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si la comprobación se realizó correctamente; de lo contrario, `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureVerification (método)](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx (método)](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
