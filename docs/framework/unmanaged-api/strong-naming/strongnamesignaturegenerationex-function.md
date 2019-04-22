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
ms.openlocfilehash: e5d60b9a9ae566b5bd686b27b2e09861a8414979
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190020"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx (Función)
Genera una firma de nombre seguro para el ensamblado especificado, según las marcas especificadas.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.  
  
 `wszKeyContainer`  
 [in] Nombre del contenedor de claves que contiene el par de claves pública y privada.  
  
 Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP). En este caso, el par de claves almacenadas en el contenedor se usa para firmar el archivo.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).  
  
 `pbKeyBlob`  
 [in] Un puntero a la par de claves pública y privada. Este par está en el formato creado por Win32 `CryptExportKey` función. Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.  
  
 `cbKeyBlob`  
 [in] El tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Un puntero a la ubicación a la que common language runtime devuelve la firma. Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.  
  
 Si `ppbSignatureBlob` es no nulo, common language runtime asigna espacio en el que se va a devolver la firma. El llamador debe liberar este espacio mediante el [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.  
  
 `pcbSignatureBlob`  
 [out] El tamaño, en bytes, de la firma devuelta.  
  
 `dwFlags`  
 [in] Uno o varios de los siguientes valores:  
  
-   `SN_SIGN_ALL_FILES` (0 x 00000001): volver a calcular todos los códigos hash para módulos vinculados.  
  
-   `SN_TEST_SIGN` (0 x 00000002): el ensamblado de prueba de inicio de sesión.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.  
  
 La firma puede se almacenan directamente en el archivo, o se devuelve al llamador.  
  
 Si `SN_SIGN_ALL_FILES` se especifica, pero no se incluye una clave pública (ambos `pbKeyBlob` y `wszFilePath` son null), se vuelven a calcular los valores hash de los módulos vinculados, pero no se ha vuelto a firmar el ensamblado.  
  
 Si `SN_TEST_SIGN` se especifica, el encabezado de common language runtime no se modifica para indicar que el ensamblado está firmado con un nombre seguro.  
  
 Si el `StrongNameSignatureGenerationEx` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureGenerationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
