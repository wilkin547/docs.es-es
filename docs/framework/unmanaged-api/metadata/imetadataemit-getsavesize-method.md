---
title: IMetaDataEmit::GetSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
ms.openlocfilehash: 5cb202f5284c1c18545ec750b2fa0f04d4b0d2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722068"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize (Método)

Obtiene el tamaño binario estimado del ensamblado y sus metadatos en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `fSave`  
 de Valor de la enumeración [CorSaveSize (](corsavesize-enumeration.md) que especifica si se va a obtener un tamaño exacto o aproximado. Solo tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:  
  
- cssAccurate devuelve el tamaño exacto de guardado, pero tarda más tiempo en calcular.  
  
- cssQuick devuelve un tamaño, rellenado por seguridad, pero tarda menos tiempo en calcularse.  
  
- cssDiscardTransientCAs indica `GetSaveSize` que puede eliminar los atributos personalizados que se pueden descartar.  
  
 `pdwSaveSize`  
 enuncia Puntero al tamaño necesario para guardar el archivo.  
  
## <a name="remarks"></a>Comentarios  

 `GetSaveSize` calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual. (Una llamada al método [IMetaDataEmit:: SaveToStream (](imetadataemit-savetostream-method.md) emitiría este número de bytes).  
  
 Si el autor de la llamada implementa la interfaz [IMapToken](imaptoken-interface.md) (a través de [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)), `GetSaveSize` realizará dos pases sobre los metadatos para optimizarlos y comprimirlos. De lo contrario, no se realiza ninguna optimización.  
  
 Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas en tiempo de importación. Este paso suele tener como resultado la mudanza de registros, con el efecto secundario de que se invalidan los tokens retenidos por la herramienta para futuras referencias. Sin embargo, los metadatos no informan al llamador de estos cambios de token hasta después del segundo paso. En el segundo paso, se realizan varias optimizaciones que están diseñadas para reducir el tamaño total de los metadatos, como la optimización de los tokens (enlace temprano) `mdTypeRef` y los `mdMemberRef` tokens cuando se hace referencia a un tipo o miembro declarado en el ámbito de metadatos actual. En este paso, se produce otra ronda de asignación de tokens. Después de este paso, el motor de metadatos notifica al llamador, a través `IMapToken` de su interfaz, los valores de token modificados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
