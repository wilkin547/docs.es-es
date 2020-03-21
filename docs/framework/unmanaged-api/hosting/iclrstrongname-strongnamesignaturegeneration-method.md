---
title: ICLRStrongName::StrongNameSignatureGeneration (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178053"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration (Método)
Genera una firma de nombres seguros para el ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [en] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.  
  
 `wszKeyContainer`  
 [en] El nombre del contenedor de claves que contiene el par de claves pública y privada.  
  
 Si `pbKeyBlob` es `wszKeyContainer` null, debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP). En este caso, el par de claves almacenado en el contenedor se utiliza para firmar el archivo.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.  
  
 Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits. No se admiten otros tipos de claves en este momento.  
  
 `pbKeyBlob`  
 [en] Un puntero al par de claves pública y privada. Este par tiene el formato creado `CryptExportKey` por la función Win32. Si `pbKeyBlob` es null, se supone `wszKeyContainer` que el contenedor de claves especificado por contiene el par de claves.  
  
 `cbKeyBlob`  
 [en] El tamaño, en `pbKeyBlob`bytes, de .  
  
 `ppbSignatureBlob`  
 [fuera] Puntero a la ubicación a la que Common Language Runtime devuelve la firma. Si `ppbSignatureBlob` es null, el tiempo de ejecución `wszFilePath`almacena la firma en el archivo especificado por .  
  
 Si `ppbSignatureBlob` no es null, Common Language Runtime asigna espacio en el que devolver la firma. El llamador debe liberar este espacio mediante el método [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbSignatureBlob`  
 [fuera] El tamaño, en bytes, de la firma devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).  
  
## <a name="remarks"></a>Observaciones  
 Especifique null `wszFilePath` for para calcular el tamaño de la firma sin crear la firma.  
  
 La firma se puede almacenar directamente en el archivo o devolver se devuelve al autor de la llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
