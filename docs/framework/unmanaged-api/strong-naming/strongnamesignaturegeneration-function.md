---
title: StrongNameSignatureGeneration (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176908"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration (Función)
Genera una firma de nombres seguros para el ensamblado especificado.  
  
 Esta función ha quedado en desuso. Utilice el método [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
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
  
 Si `ppbSignatureBlob` no es null, Common Language Runtime asigna espacio en el que devolver la firma. El llamador debe liberar este espacio mediante la [strongNameFreeBuffer](strongnamefreebuffer-function.md) función.  
  
 `pcbSignatureBlob`  
 [fuera] El tamaño, en bytes, de la firma devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`una finalización exitosa; de `false`lo contrario, .  
  
## <a name="remarks"></a>Observaciones  
 Especifique null `wszFilePath` for para calcular el tamaño de la firma sin crear la firma.  
  
 La firma se puede almacenar directamente en el archivo o devolver se devuelve al autor de la llamada.  
  
 Si `StrongNameSignatureGeneration` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Método StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
