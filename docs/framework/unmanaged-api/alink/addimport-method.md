---
title: AddImport (Método)
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446661"
---
# <a name="addimport-method"></a>AddImport (Método)
Agrega importaciones al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 IDENTIFICADOR único del ensamblado que se va a aumentar.  
  
 `ImportToken`  
 IDENTIFICADOR único, recuperado del [método importFile](importfile-method.md), del archivo que se va a importar.  
  
 `dwFlags`  
 Marcas de FileDef COM+, como `ffContainsNoMetaData` y `ffWriteable`. `dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Puntero al token que recibe el identificador del archivo resultante.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
