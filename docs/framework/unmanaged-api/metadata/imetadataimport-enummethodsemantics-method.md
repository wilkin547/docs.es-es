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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16cfa6df6251cd67860155cb8092e77a835eaaef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992425"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics (Método)
Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in, out] Un puntero en el enumerador. Esto debe ser NULL para la primera llamada de este método.  
  
 `mb`  
 [in] Un token de MethodDef que limita el ámbito de la enumeración.  
  
 `rEventProp`  
 [out] Matriz utilizada para almacenar los eventos o propiedades.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rEventProp`.  
  
 `pcEventProp`  
 [out] El número de eventos o propiedades que se devuelven en `rEventProp`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` se devolvió correctamente.|  
|`S_FALSE`|No existen eventos ni propiedades que enumerar. En ese caso, `pcEventProp` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Definen muchos tipos de common language runtime *propiedad* `Changed` eventos y `On` *propiedad* `Changed` métodos relacionados con sus propiedades. Por ejemplo, el <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo define un <xref:System.Windows.Forms.Control.Font%2A> propiedad, un <xref:System.Windows.Forms.Control.FontChanged> evento y un <xref:System.Windows.Forms.Control.OnFontChanged%2A> método. El método de descriptor de acceso set de la <xref:System.Windows.Forms.Control.Font%2A> propiedad llamadas <xref:System.Windows.Forms.Control.OnFontChanged%2A> método, que a su vez desencadena el <xref:System.Windows.Forms.Control.FontChanged> eventos. Se llamaría a `EnumMethodSemantics` usando el MethodDef de <xref:System.Windows.Forms.Control.OnFontChanged%2A> para obtener referencias a la <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.Control.FontChanged> eventos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
