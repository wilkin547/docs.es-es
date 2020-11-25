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
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733729"
---
# <a name="setmanifestfile-method"></a>SetManifestFile (Método)

Permite especificar o restablecer el archivo de manifiesto que el vinculador utiliza al crear el ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `pszFile`  
  
 Nombre del archivo de manifiesto cuyo contenido se coloca en el BLOB de recursos de Win32.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="remarks"></a>Comentarios  

 Llame a este método antes de solicitar el Win32ResBlob. El valor del `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST. Cuando se llama con un parámetro de NULL, se borra cualquier manifiesto leído previamente. Esto permite restablecer el estado del enlazador con respecto al tiempo de inicialización.  
  
## <a name="requirements"></a>Requisitos  

 Requiere aLink. h  
  
## <a name="see-also"></a>Consulte también

- [IALink3 (Interfaz)](ialink3-interface.md)
- [API de ALink](index.md)
- [IALink (Interfaz)](ialink-interface.md)
- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
