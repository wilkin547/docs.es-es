---
title: "SetManifestFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf48153454fbb2c24dc3f1cfe1f82deefa4ee723
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="setmanifestfile-method"></a>SetManifestFile (Método)
Permite especificar o restablecer el archivo de manifiesto que el vinculador usa al crear el ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pszFile`  
  
 El nombre del archivo de manifiesto cuyo contenido se coloca en el blob de recursos de Win32.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="remarks"></a>Comentarios  
 Esto se llama antes de solicitar la Win32ResBlob. El valor de la `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST. Cuando se llama mediante un parámetro es null, se borran los manifiestos leídos previamente. Esto permite restablecer el estado del vinculador que el de tiempo de inicialización.  
  
## <a name="requirements"></a>Requisitos  
 Requiere aLink.h  
  
## <a name="see-also"></a>Vea también  
 [IALink3 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
