---
description: 'Más información sobre: método Getfiledef ('
title: GetFileDef (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
ms.openlocfilehash: 5d44336e686ca565f468fb95ce5290ee41d5e16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718452"
---
# <a name="getfiledef-method"></a>GetFileDef (Método)

Recupera el token de FileDef real que se usa en los metadatos (en contraposición al token asignado por ALink).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
 `TargetFile`  
 Token del archivo agregado tal y como se recuperó del método AddFile o del método addImport (.  
  
 `pScope`  
 Recibe el token FileDef.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink2 (Interfaz)](ialink2-interface.md)
- [IALink (Interfaz)](ialink-interface.md)
- [API de ALink](index.md)
