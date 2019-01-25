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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc1664551683066a33fb52e16e4909506601f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588696"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout (Método)
Se completa el diseño de campos para una clase que se ha definido por una llamada anterior a [DefineTypeDef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] Un `mdTypeDef` símbolo (token) que especifica la clase que se coloquen.  
  
 `dwPackSize`  
 [in] El tamaño de empaquetado: 1, 2, 4, 8 ó 16 bytes. El tamaño de empaquetado es el número de bytes entre los campos adyacentes.  
  
 `rFieldOffsets`  
 [in] Una matriz de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) estructuras, cada uno de los cuales especifica un campo de la clase y el campo de desplazamiento dentro de la clase. Finalice la matriz con `mdTokenNil`.  
  
 `ulClassSize`  
 [in] El tamaño, en bytes, de la clase.  
  
## <a name="remarks"></a>Comentarios  
 La clase inicialmente se define mediante una llamada a la [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) método y especifique uno de los tres diseños para los campos de la clase: automático, secuencial o explícito. Normalmente, debe usar el diseño automático y dejar que el tiempo de ejecución a elegir la mejor manera de diseñar los campos.  
  
 Sin embargo, es posible que desea que los campos que disponen de acuerdo con la disposición en el código no administrado. En este caso, elija un diseño secuencial o explícito y llame a `SetClassLayout` para completar el diseño de los campos:  
  
-   Diseño secuencial: Especifique el tamaño de empaquetado. Un campo se alinea según su tamaño natural o el tamaño de empaquetado, sea cual sea resultados en el desplazamiento del campo más pequeño. Establecer `rFieldOffsets` y `ulClassSize` a cero.  
  
-   Diseño explícito: Especificar el desplazamiento de cada campo o especificar el tamaño de la clase y el tamaño de empaquetado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
