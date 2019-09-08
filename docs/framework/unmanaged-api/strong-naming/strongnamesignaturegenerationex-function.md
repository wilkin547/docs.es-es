---
title: StrongNameSignatureGenerationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798983"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx (Función)
Genera una firma de nombre seguro para el ensamblado especificado, según las marcas especificadas.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameSignatureGenerationEx (](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.  
  
 `wszKeyContainer`  
 de Nombre del contenedor de claves que contiene el par de claves pública y privada.  
  
 Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP). En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.  
  
 `pbKeyBlob`  
 de Puntero al par de claves pública y privada. Este par está en el formato creado por la función `CryptExportKey` de Win32. Si `pbKeyBlob` es null, se supone que el contenedor `wszKeyContainer` de claves especificado por contiene el par de claves.  
  
 `cbKeyBlob`  
 de Tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma. Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath`.  
  
 Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma. El autor de la llamada debe liberar este espacio mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbSignatureBlob`  
 enuncia Tamaño, en bytes, de la firma devuelta.  
  
 `dwFlags`  
 de Uno o varios de los siguientes valores:  
  
- `SN_SIGN_ALL_FILES`(0x00000001): vuelve a calcular todos los valores hash para los módulos vinculados.  
  
- `SN_TEST_SIGN`(0x00000002): prueba-firma del ensamblado.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 Especifique NULL para `wszFilePath` para calcular el tamaño de la firma sin crear la firma.  
  
 La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.  
  
 Si `SN_SIGN_ALL_FILES` se especifica, pero no se incluye una clave pública `pbKeyBlob` (y `wszFilePath` son NULL), se vuelven a calcular los valores hash de los módulos vinculados, pero no se vuelve a firmar el ensamblado.  
  
 Si `SN_TEST_SIGN` se especifica, el encabezado Common Language Runtime no se modifica para indicar que el ensamblado está firmado con un nombre seguro.  
  
 Si la `StrongNameSignatureGenerationEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureGenerationEx (método)](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration (método)](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
