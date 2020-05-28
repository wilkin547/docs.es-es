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
ms.openlocfilehash: a18583ce807ffa672811f3a0cd1e744233f6eb30
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008838"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout (Método)
Completa el diseño de los campos de una clase definida por una llamada anterior al [método DefineTypeDef](imetadataemit-definetypedef-method.md).  
  
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
 de `mdTypeDef`Token que especifica la clase que se va a disponer.  
  
 `dwPackSize`  
 de Tamaño de empaquetado: 1, 2, 4, 8 o 16 bytes. El tamaño de empaquetado es el número de bytes entre los campos adyacentes.  
  
 `rFieldOffsets`  
 de Matriz de estructuras [COR_FIELD_OFFSET](cor-field-offset-structure.md) , cada una de las cuales especifica un campo de la clase y el desplazamiento del campo dentro de la clase. Finalice la matriz con `mdTokenNil` .  
  
 `ulClassSize`  
 de Tamaño, en bytes, de la clase.  
  
## <a name="remarks"></a>Comentarios  
 La clase se define inicialmente llamando al método [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) y especificando uno de los tres diseños para los campos de la clase: automático, secuencial o explícito. Normalmente, usaría el diseño automático y dejar que el tiempo de ejecución elija la mejor manera de diseñar los campos.  
  
 Sin embargo, es posible que desee que los campos estén dispuestos según la disposición que utiliza el código no administrado. En este caso, elija diseño secuencial o explícito y llame `SetClassLayout` a para completar el diseño de los campos:  
  
- Diseño secuencial: especifique el tamaño de empaquetado. Un campo está alineado según su tamaño natural o el tamaño de empaquetado, lo que sea el desplazamiento más pequeño del campo. Establezca `rFieldOffsets` y `ulClassSize` en cero.  
  
- Diseño explícito: especifique el desplazamiento de cada campo o especifique el tamaño de la clase y el tamaño de empaquetado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
