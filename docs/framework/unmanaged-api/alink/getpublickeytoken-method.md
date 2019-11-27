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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447243"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken (Método)
Recupera el token de clave pública de un contenedor de claves o keyfile determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 Dirección en la que se va a almacenar el token de clave.  
  
 `pcbPublicKeyToken`  
 Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`. En la devolución, contiene el número real de bytes utilizados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink2 (interfaz)](ialink2-interface.md)
- [IALink (interfaz)](ialink-interface.md)
- [API de ALink](index.md)
