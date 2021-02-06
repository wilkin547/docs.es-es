---
description: 'Más información sobre: método Setmanifestfile ('
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
ms.openlocfilehash: fe91c7f2b4e6f58a0a740de84e055ead49adb77d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662330"
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
  
## <a name="remarks"></a>Observaciones  

 Llame a este método antes de solicitar el Win32ResBlob. El valor del `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST. Cuando se llama con un parámetro de NULL, se borra cualquier manifiesto leído previamente. Esto permite restablecer el estado del enlazador con respecto al tiempo de inicialización.  
  
## <a name="requirements"></a>Requisitos  

 Requiere aLink. h  
  
## <a name="see-also"></a>Vea también

- [IALink3 (Interfaz)](ialink3-interface.md)
- [API de ALink](index.md)
- [IALink (Interfaz)](ialink-interface.md)
- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
