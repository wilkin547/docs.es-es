---
title: GetScope2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: a5b080443be94d5a298cc67591914d87470e6f48
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447189"
---
# <a name="getscope2-method"></a>GetScope2 (Método)
Obtiene un ámbito de importación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 IDENTIFICADOR del ensamblado de destino.  
  
 `FileToken`  
 IDENTIFICADOR del archivo desde el que se va a importar.  
  
 `dwScope`  
 Ámbito de base cero que se va a importar.  
  
 `ppImportScope`  
 Recibe un puntero a la interfaz de [interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) para el ámbito indicado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink2 (interfaz)](ialink2-interface.md)
- [IALink (interfaz)](ialink-interface.md)
- [API de ALink](index.md)
