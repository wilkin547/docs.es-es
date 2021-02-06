---
description: 'Más información sobre: método ImportTypes ('
title: ImportTypes (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 9a30c735ca2c9ad0f945628c3de1eb1bb56efe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662629"
---
# <a name="importtypes-method"></a>ImportTypes (Método)

Inicia la importación de tipos de cada ámbito importado mediante el [método importFile](importfile-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado en el que se va a importar.  
  
 `FileToken`  
 IDENTIFICADOR del archivo desde el que se va a importar.  
  
 `dwScope`  
 Ámbito de base cero que se va a importar.  
  
 `phEnum`  
 Recibe el identificador de enumerador para los tipos de este ámbito.  
  
 `ppImportScope`  
 Opcionalmente, recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) .  
  
 `pdwCountOfTypes`  
 Opcionalmente, recibe el recuento de tipos en el ámbito indicado.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
