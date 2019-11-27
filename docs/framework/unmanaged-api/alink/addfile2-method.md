---
title: AddFile2 (Método)
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446662"
---
# <a name="addfile2-method"></a>AddFile2 (Método)
Agrega archivos al ensamblado. También se puede usar para crear módulos sin enlazar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 IDENTIFICADOR del ensamblado al que se agrega el archivo.  
  
 `pszFilename`  
 Nombre del archivo que se va a agregar.  
  
 `dwFlags`  
 Marcas de `FileDef` COM+, como `ffContainsNoMetaData` y `ffWriteable`. `dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interfaz para la interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .  
  
 `pFileToken`  
 Recibe el identificador del archivo que se va a agregar.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink2 (interfaz)](ialink2-interface.md)
- [IALink (interfaz)](ialink-interface.md)
- [API de ALink](index.md)
