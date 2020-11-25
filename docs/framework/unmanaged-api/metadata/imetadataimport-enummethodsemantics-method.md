---
title: IMetaDataImport::EnumMethodSemantics (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 3d14aea92633c944d21d867c8152767ae6f1f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720976"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics (Método)

Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `mb`  
 de Un token MethodDef que limita el ámbito de la enumeración.  
  
 `rEventProp`  
 enuncia Matriz que se usa para almacenar los eventos o propiedades.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rEventProp`.  
  
 `pcEventProp`  
 enuncia Número de eventos o propiedades devueltos en `rEventProp` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` se devolvió correctamente.|  
|`S_FALSE`|No hay eventos ni propiedades para enumerar. En ese caso, `pcEventProp` es cero.|  
  
## <a name="remarks"></a>Comentarios  

 Muchos tipos de Common Language Runtime *Property* definen `Changed` los eventos de propiedad y `On` *Property* `Changed` los métodos de propiedad relacionados con sus propiedades. Por ejemplo, el <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo define una <xref:System.Windows.Forms.Control.Font%2A> propiedad, un <xref:System.Windows.Forms.Control.FontChanged> evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método. El método de descriptor de acceso set de la <xref:System.Windows.Forms.Control.Font%2A> propiedad llama al <xref:System.Windows.Forms.Control.OnFontChanged%2A> método, que a su vez provoca el <xref:System.Windows.Forms.Control.FontChanged> evento. Llamaría al `EnumMethodSemantics` uso de MethodDef para <xref:System.Windows.Forms.Control.OnFontChanged%2A> para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y al <xref:System.Windows.Forms.Control.FontChanged> evento.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
