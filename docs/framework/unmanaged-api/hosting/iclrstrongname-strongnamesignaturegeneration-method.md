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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165791"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration (Método)
Genera una firma de nombres seguros para el ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.  
  
 `wszKeyContainer`  
 [in] Nombre del contenedor de claves que contiene el par de claves pública y privada.  
  
 Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP). En este caso, el par de claves almacenadas en el contenedor se usa para firmar el archivo.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).  
  
 Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma. Se admite ningún otro tipo de claves en este momento.  
  
 `pbKeyBlob`  
 [in] Un puntero a la par de claves pública y privada. Este par está en el formato creado por Win32 `CryptExportKey` función. Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.  
  
 `cbKeyBlob`  
 [in] El tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Un puntero a la ubicación a la que common language runtime devuelve la firma. Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.  
  
 Si `ppbSignatureBlob` es no nulo, common language runtime asigna espacio en el que se va a devolver la firma. El llamador debe liberar este espacio mediante el uso de la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.  
  
 `pcbSignatureBlob`  
 [out] El tamaño, en bytes, de la firma devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.  
  
 La firma se puede almacenar directamente en el archivo o la devuelve al llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureGenerationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
