---
title: EnumCustomAttributes (Método)
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446471"
---
# <a name="enumcustomattributes-method"></a>EnumCustomAttributes (Método)
Recupera los atributos personalizados de nivel de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `hEnum`  
 Identificador del enumerador.  
  
 `tkType`  
 Tipo de atributos que se van a enumerar. Use `mdTokenNill` para todos los atributos.  
  
 `rCustomValues`  
 Recibe tokens de atributos personalizados.  
  
 `cMax`  
 Especifica el tamaño de `rCustomValues` matriz.  
  
 `pcCustomValues`  
 Opcionalmente, recibe el recuento de valores de token.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
