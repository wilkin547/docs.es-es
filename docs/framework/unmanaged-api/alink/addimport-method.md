---
description: 'Más información sobre: método addImport ('
title: Método AddImport
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
ms.openlocfilehash: 9dca26501e66313b0932caf1288db7c909154e1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638605"
---
# <a name="addimport-method"></a>Método AddImport

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
 Marcas de FileDef COM+ como `ffContainsNoMetaData` y `ffWriteable` . `dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Puntero al token que recibe el identificador del archivo resultante.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
