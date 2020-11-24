---
title: LinkResource (Método)
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690452"
---
# <a name="linkresource-method"></a>LinkResource (Método)

Vínculos en un recurso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
 `pszFileName`  
 Nombre del archivo.  
  
 `pszNewLocation`  
 Nuevo nombre de archivo opcional. Si no es NULL, se `pszFileName` copiará en pszNewLocation.  
  
 `pszResourceName`  
 Nombre del recurso.  
  
 `dwFlags`  
 Marcas de accesibilidad como `mrPublic` y `mrPrivate` . Este parámetro se puede pasar al [método DefineManifestResource (](../metadata/imetadataassemblyemit-definemanifestresource-method.md).  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h.  
  
## <a name="see-also"></a>Consulte también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
