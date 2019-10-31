---
title: StrongNameKeyGen (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: 79b2235e3645c89c2cd9ebcce079d5eb7efdd162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128738"
---
# <a name="strongnamekeygen-function"></a>StrongNameKeyGen (Función)
Crea un par de claves pública y privada para su uso en nombres seguros.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamekeygen (](../hosting/iclrstrongname-strongnamekeygen-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 de Nombre del contenedor de claves solicitado. `wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.  
  
 `dwFlags`  
 de Especifica si se debe dejar registrada la clave. Se admiten los siguientes valores:  
  
- 0x00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.  
  
- 0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.  
  
 `ppbKeyBlob`  
 enuncia Par de claves pública y privada devuelta.  
  
 `pcbKeyBlob`  
 enuncia Tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 La función `StrongNameKeyGen` crea una clave de 1024 bits. Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la función `StrongNameKeyGen` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameKeyGen (método)](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [StrongNameKeyGenEx (método)](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
