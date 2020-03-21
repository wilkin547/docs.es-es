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
ms.openlocfilehash: 40df78cdf99c2e0f53be9664f3f5c6386b6c6f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179398"
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
 ID del ensamblado de destino.  
  
 `FileToken`  
 ID del archivo desde el que se va a importar.  
  
 `dwScope`  
 Alcance de base cero que se va a importar.  
  
 `ppImportScope`  
 Recibe el puntero a [Interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) interfaz para el ámbito indicado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se realiza correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Consulte también

- [IALink2 (interfaz)](ialink2-interface.md)
- [IALink (interfaz)](ialink-interface.md)
- [API de ALink](index.md)
