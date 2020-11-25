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
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719273"
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
 [in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .  
  
 `pfWasVerified`  
 [out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` . `pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Si la comprobación se realizó correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 `StrongNameSignatureVerificationEx` proporciona una funcionalidad similar a la función [strongnamesignatureverification (](strongnamesignatureverification-function.md) . Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son de tipo `BOOLEAN` en lugar de `DWORD` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en mscoree.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Método StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
