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
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450079"
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
 enuncia Número de eventos o propiedades devueltos en `rEventProp`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` devolvió correctamente.|  
|`S_FALSE`|No hay eventos ni propiedades para enumerar. En ese caso, `pcEventProp` es cero.|  
  
## <a name="remarks"></a>Comentarios  
 Muchos tipos de Common Language Runtime definen eventos de`Changed` de *propiedad* y `On`de los métodos de`Changed` de *propiedad* relacionados con sus propiedades. Por ejemplo, el tipo <xref:System.Windows.Forms.Control?displayProperty=nameWithType> define una propiedad <xref:System.Windows.Forms.Control.Font%2A>, un evento <xref:System.Windows.Forms.Control.FontChanged> y un método <xref:System.Windows.Forms.Control.OnFontChanged%2A>. El método de descriptor de acceso set de la propiedad <xref:System.Windows.Forms.Control.Font%2A> llama a <xref:System.Windows.Forms.Control.OnFontChanged%2A> método, que a su vez provoca el evento <xref:System.Windows.Forms.Control.FontChanged>. Llamaría a `EnumMethodSemantics` mediante MethodDef para <xref:System.Windows.Forms.Control.OnFontChanged%2A> para obtener referencias a la propiedad <xref:System.Windows.Forms.Control.Font%2A> y al evento <xref:System.Windows.Forms.Control.FontChanged>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
