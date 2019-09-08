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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798923"
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
 de para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; de lo contrario, `false`. `true`  
  
 `pfWasVerified`  
 enuncia Si se ha comprobado la firma de nombre seguro; en caso contrario, `false`. `true` `pfWasVerified`también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Si la comprobación se realizó correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 `StrongNameSignatureVerificationEx`proporciona una funcionalidad similar a la función [strongnamesignatureverification (](strongnamesignatureverification-function.md) . Sin embargo, el segundo parámetro de entrada y el parámetro `StrongNameSignatureVerificationEx` de salida para `BOOLEAN` son de tipo `DWORD`en lugar de.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureVerificationEx (método)](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification (método)](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
