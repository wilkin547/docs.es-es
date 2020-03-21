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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176934"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey (Función)
Obtiene la clave pública de un par de claves pública y privada. El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección sin procesar de bytes.  
  
 Esta función ha quedado en desuso. Utilice el [método ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.  
  
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
 [en] El nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es `szKeyContainer` null, debe especificar un contenedor válido dentro del CSP. En este `StrongNameGetPublicKey` caso, extrae la clave pública del par de claves almacenado en el contenedor.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.  
  
 Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits. No se admiten otros tipos de claves en este momento.  
  
 `pbKeyBlob`  
 [en] Un puntero al par de claves pública y privada. Este par tiene el formato creado `CryptExportKey` por la función Win32. Si `pbKeyBlob` es null, se supone `szKeyContainer` que el contenedor de claves especificado por contiene el par de claves.  
  
 `cbKeyBlob`  
 [en] El tamaño, en `pbKeyBlob`bytes, de .  
  
 `ppbPublicKeyBlob`  
 [fuera] La clave pública devuelta BLOB. Common `ppbPublicKeyBlob` Language Runtime asigna el parámetro y lo devuelve al autor de la llamada. El llamador debe liberar la memoria mediante el uso de la [StrongNameFreeBuffer](strongnamefreebuffer-function.md) función.  
  
 `pcbPublicKeyBlob`  
 [fuera] El tamaño de la clave pública devuelta BLOB.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`una finalización exitosa; de `false`lo contrario, .  
  
## <a name="remarks"></a>Observaciones  
 La clave pública se encuentra en un [PublicKeyBlob](publickeyblob-structure.md) estructura.  
  
 Si `StrongNameGetPublicKey` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Método StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob (Estructura)](publickeyblob-structure.md)
