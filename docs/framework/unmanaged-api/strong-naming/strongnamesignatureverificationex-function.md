---
title: StrongNameSignatureVerificationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
ms.openlocfilehash: ca428d680df1710d8e74441d9945d4c3545b0482
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121145"
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx (Función)
Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamesignatureverificationex (](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.  
  
 `fForceVerification`  
 [in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; de lo contrario, `false`.  
  
 `pfWasVerified`  
 [out] `true` si se ha comprobado la firma de nombre seguro; de lo contrario, `false`. `pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si la comprobación se realizó correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 `StrongNameSignatureVerificationEx` proporciona una funcionalidad similar a la función [strongnamesignatureverification (](strongnamesignatureverification-function.md) . Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son del tipo `BOOLEAN` en lugar de `DWORD`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureVerificationEx (método)](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification (método)](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
