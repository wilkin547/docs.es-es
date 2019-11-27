---
title: EndMerge (Método)
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: cacf7eab1e53f590ad46fd98ed2f5dcbd14cd30a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434406"
---
# <a name="endmerge-method"></a>EndMerge (Método)
Indica que todos los atributos personalizados se han combinado en el ámbito de emisión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
