---
description: 'Más información acerca de: AddFile (método)'
title: Método AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 5e1253587298b2c1559c72dced43ec70dc169090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638631"
---
# <a name="addfile-method"></a>Método AddFile

Agrega archivos al ensamblado. También se puede usar para crear módulos sin enlazar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR único del ensamblado que se va a aumentar.  
  
 `pszFilename`  
 Nombre completo del archivo que se va a agregar.  
  
 `dwFlags`  
 Marcas de FileDef COM+ como `ffContainsNoMetaData` y `ffWriteable` . `dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 [IMetaDataEmit](../metadata/imetadataemit-interface.md) interfaz interface que se va a usar para emitir metadatos, si es necesario.  
  
 `pFileToken`  
 Puntero al lugar donde se almacenará el identificador único del archivo agregado.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
