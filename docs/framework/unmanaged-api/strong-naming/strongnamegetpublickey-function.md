---
title: StrongNameGetPublicKey (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: 966a2a628f30f1999688da7b6ba435c1d6cb830c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094662"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey (Función)
Obtiene la clave pública de un par de claves pública y privada. El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameGetPublicKey (](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szKeyContainer`  
 de Nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP. En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves almacenado en el contenedor.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.  
  
 Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits. En este momento no se admite ningún otro tipo de clave.  
  
 `pbKeyBlob`  
 de Puntero al par de claves pública y privada. Este par está en el formato creado por la función `CryptExportKey` de Win32. Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.  
  
 `cbKeyBlob`  
 de Tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 enuncia El BLOB de clave pública devuelto. El Common Language Runtime asigna el parámetro `ppbPublicKeyBlob` y se devuelve al autor de la llamada. El autor de la llamada debe liberar la memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbPublicKeyBlob`  
 enuncia Tamaño del BLOB de clave pública devuelto.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 La clave pública está contenida en una estructura [PublicKeyBlob](publickeyblob-structure.md) .  
  
 Si la función `StrongNameGetPublicKey` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetPublicKey (método)](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey (método)](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob (estructura)](publickeyblob-structure.md)
