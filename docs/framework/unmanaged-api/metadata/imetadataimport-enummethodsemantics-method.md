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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175465"
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
 [adentro, fuera] Un puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `mb`  
 [en] Un token MethodDef que limita el ámbito de la enumeración.  
  
 `rEventProp`  
 [fuera] Matriz utilizada para almacenar los eventos o propiedades.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rEventProp`.  
  
 `pcEventProp`  
 [fuera] El número de eventos `rEventProp`o propiedades devueltos en .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`regresó con éxito.|  
|`S_FALSE`|No hay eventos ni propiedades que enumerar. En ese `pcEventProp` caso, es cero.|  
  
## <a name="remarks"></a>Observaciones  
 Muchos tipos de *Property* `Changed` Common Language `On`Runtime definen eventos Property y métodos *Property* `Changed` relacionados con sus propiedades. Por ejemplo, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> el <xref:System.Windows.Forms.Control.Font%2A> tipo define <xref:System.Windows.Forms.Control.FontChanged> una propiedad, un evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método. El método de <xref:System.Windows.Forms.Control.Font%2A> descriptor <xref:System.Windows.Forms.Control.OnFontChanged%2A> de acceso set de <xref:System.Windows.Forms.Control.FontChanged> la propiedad llama al método, que a su vez provoca el evento. Se llamaría `EnumMethodSemantics` a través <xref:System.Windows.Forms.Control.OnFontChanged%2A> de la MethodDef para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.Control.FontChanged> evento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
