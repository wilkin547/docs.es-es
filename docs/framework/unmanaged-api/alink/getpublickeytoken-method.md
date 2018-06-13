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
ms.openlocfilehash: 94a473d00110c07615ccdfc98bb8944e40dc30e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405478"
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
  
#### <a name="parameters"></a>Parámetros  
 `pszKeyFile`  
 Nombre de archivo de la clave.  
  
 `pszKeyContainer`  
 Nombre del contenedor de claves.  
  
 `pvPublicKeyToken`  
 Dirección donde se almacenará el token de clave.  
  
 `pcbPublicKeyToken`  
 Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`. Tras la devolución, contiene el número real de bytes que se usa.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
