---
title: IMetaDataEmit::SetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177568"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout (Método)
Completa el diseño de campos para una clase definida por una llamada anterior al [método DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 [en] Un `mdTypeDef` token que especifica la clase que se va a establecer.  
  
 `dwPackSize`  
 [en] El tamaño de embalaje: 1, 2, 4, 8 o 16 bytes. El tamaño de embalaje es el número de bytes entre campos adyacentes.  
  
 `rFieldOffsets`  
 [en] Matriz de [estructuras COR_FIELD_OFFSET,](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) cada una de las cuales especifica un campo de la clase y el desplazamiento del campo dentro de la clase. Termine la `mdTokenNil`matriz con .  
  
 `ulClassSize`  
 [en] El tamaño, en bytes, de la clase.  
  
## <a name="remarks"></a>Observaciones  
 La clase se define inicialmente llamando al método [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) y especificando uno de los tres diseños para los campos de la clase: automatic, sequential o explicit. Normalmente, usaría el diseño automático y dejaría que el tiempo de ejecución elija la mejor manera de diseñar los campos.  
  
 Sin embargo, es posible que desee que los campos se establezcan de acuerdo con la disposición que utiliza el código no administrado. En este caso, elija el diseño `SetClassLayout` secuencial o explícito y llame para completar el diseño de los campos:  
  
- Diseño secuencial: especifique el tamaño de embalaje. Un campo se alinea según su tamaño natural o el tamaño de embalaje, lo que resulte en el desplazamiento más pequeño del campo. Ajuste `rFieldOffsets` `ulClassSize` y a cero.  
  
- Diseño explícito: especifique el desplazamiento de cada campo o especifique el tamaño de clase y el tamaño de embalaje.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
