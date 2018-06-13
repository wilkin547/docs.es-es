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
ms.openlocfilehash: e22cf8e540bfdb53ad243640dac110b5750e53e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449126"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout (Método)
Complete el diseño de campos para una clase que se ha definido por una llamada anterior a [DefineTypeDef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
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
 [in] El tamaño de empaquetado: 1, 2, 4, 8 o 16 bytes. El tamaño de empaquetado es el número de bytes entre los campos adyacentes.  
  
 `rFieldOffsets`  
 [in] Una matriz de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) estructuras, cada uno de los cuales especifica un campo de la clase y el campo de desplazamiento dentro de la clase. Finalice la matriz con `mdTokenNil`.  
  
 `ulClassSize`  
 [in] El tamaño, en bytes, de la clase.  
  
## <a name="remarks"></a>Comentarios  
 La clase inicialmente se define mediante una llamada a la [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) método y especificando uno de tres diseños para los campos de la clase: automático, secuencial o explícita. Normalmente, debería usar el diseño automático y dejar que el tiempo de ejecución a elegir la mejor manera de diseñar los campos.  
  
 Sin embargo, puede que los campos que se dispone de acuerdo con la organización en el código no administrado. En este caso, elija diseño secuencial o explícito y llame al método `SetClassLayout` para completar el diseño de los campos:  
  
-   Un diseño secuencial: especifique el tamaño de empaquetado. Un campo se alinea según su tamaño natural o el tamaño de empaquetado, sea cual sea resultados en el desplazamiento más pequeño del campo. Establecer `rFieldOffsets` y `ulClassSize` a cero.  
  
-   Diseño explícito: especifique el desplazamiento de cada campo, o el tamaño de la clase y el tamaño de empaquetado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
