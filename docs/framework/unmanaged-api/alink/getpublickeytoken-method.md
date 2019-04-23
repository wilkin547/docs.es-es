---
title: GetPublicKeyToken (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215773"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken (Método)
Recupera el token de clave pública para un determinado archivo de clave o un contenedor de claves.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `pszKeyFile`  
 Nombre de archivo de la clave.  
  
 `pszKeyContainer`  
 Nombre del contenedor de claves.  
  
 `pvPublicKeyToken`  
 Dirección donde el token de clave es que se almacenará.  
  
 `pcbPublicKeyToken`  
 Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`. Cuando se devuelve, contiene el número real de bytes utilizados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también

- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
