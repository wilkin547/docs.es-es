---
title: SetManifestFile (Método)
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072433"
---
# <a name="setmanifestfile-method"></a>SetManifestFile (Método)
Permite especificar o restablecer el archivo de manifiesto que el vinculador usa cuando crea el ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `pszFile`  
  
 El nombre del archivo de manifiesto cuyo contenido se coloca en el blob de recursos de Win32.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="remarks"></a>Comentarios  
 Se llama antes de solicitar la Win32ResBlob. El valor de la `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se colocan en los recursos de Win32 con el identificador de RT_MANIFEST. Cuando se llama mediante un parámetro es null, se borra cualquier manifiesto leída previamente. Esto permite restablecer el estado del vinculador para que el de tiempo de inicialización.  
  
## <a name="requirements"></a>Requisitos  
 Requiere aLink.h  
  
## <a name="see-also"></a>Vea también

- [IALink3 (Interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
- [IALink (Interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
