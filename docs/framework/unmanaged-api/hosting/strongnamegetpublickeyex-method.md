---
title: StrongNameGetPublicKeyEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176232"
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx (Método)
Obtiene la clave pública de un par de claves pública y privada y especifica un algoritmo hash y un algoritmo de firma.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzKeyContainer`  
 [en] El nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es `szKeyContainer` null, debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP). En este caso, el `StrongNameGetPublicKeyEx` método extrae la clave pública del par de claves almacenado en el contenedor.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.  
  
 Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits. No se admiten otros tipos de claves en este momento.  
  
 `pbKeyBlob`  
 [en] Un puntero al par de claves pública y privada. Este par tiene el formato creado `CryptExportKey` por la función Win32. Si `pbKeyBlob` es null, se supone `szKeyContainer` que el contenedor de claves especificado por contiene el par de claves.  
  
 `cbKeyBlob`  
 [en] El tamaño, en `pbKeyBlob`bytes, de .  
  
 `ppbPublicKeyBlob`  
 [fuera] La clave pública devuelta BLOB. Common `ppbPublicKeyBlob` Language Runtime asigna el parámetro y lo devuelve al autor de la llamada. El llamador debe liberar la memoria mediante el método [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbPublicKeyBlob`  
 [fuera] El tamaño de la clave pública devuelta BLOB.  
  
 `uHashAlgId`  
 [en] El algoritmo hash de ensamblado. Consulte la sección Comentarios para obtener una lista de valores aceptados.  
  
 `uReserved`  
 [en] Reservado para uso futuro; de forma predeterminada es null.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).  
  
## <a name="remarks"></a>Observaciones  
 La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.  
  
## <a name="remarks"></a>Observaciones  
 En la tabla siguiente se muestra `uHashAlgId` el conjunto de valores aceptados para el parámetro.  
  
|Nombre|Value|  
|----------|-----------|  
|None|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob (Estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Método StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
