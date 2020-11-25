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
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710979"
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
 de Puntero al par de claves pública y privada. Este par está en el formato creado por la función de Win32 `CryptExportKey` . Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.  
  
 `cbKeyBlob`  
 de Tamaño, en bytes, de `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 enuncia El BLOB de clave pública devuelto. El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada. El autor de la llamada debe liberar la memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbPublicKeyBlob`  
 enuncia Tamaño del BLOB de clave pública devuelto.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 La clave pública está contenida en una estructura [PublicKeyBlob](publickeyblob-structure.md) .  
  
 Si la `StrongNameGetPublicKey` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Método StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob (Estructura)](publickeyblob-structure.md)
