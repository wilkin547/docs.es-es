---
title: GetScope (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: 078168ae8860f18ff6f811dcc972e3eb3c857e1d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447196"
---
# <a name="getscope-method"></a>GetScope (Método)
Obtiene un ámbito de importación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 IDENTIFICADOR único del ensamblado en el que se va a importar.  
  
 `FileToken`  
 IDENTIFICADOR único del archivo desde el que se va a importar.  
  
 `dwScope`  
 Ámbito de base cero que se va a importar.  
  
 `ppImportScope`  
 Recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) para el ámbito.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
