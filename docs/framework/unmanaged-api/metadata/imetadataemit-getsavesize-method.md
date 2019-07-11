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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7337222f7f419c68ae21d604d1673158acca85ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777390"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize (Método)
Obtiene el tamaño estimado de binario del ensamblado y sus metadatos en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fSave`  
 [in] Un valor de la [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeración que especifica si se debe obtener un tamaño exacto o aproximado. Solo los tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:  
  
- cssAccurate devuelve el tamaño de almacenamiento exacto, pero tarda más tiempo para calcular.  
  
- cssQuick devuelve un tamaño, rellenado por motivos de seguridad, pero tarda menos tiempo para calcular.  
  
- indica cssDiscardTransientCAs `GetSaveSize` que puede iniciar lejos los atributos personalizados que se puede descartar.  
  
 `pdwSaveSize`  
 [out] Un puntero al tamaño que es necesario para guardar el archivo.  
  
## <a name="remarks"></a>Comentarios  
 `GetSaveSize` calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual. (Una llamada a la [SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) método emitiría este número de bytes.)  
  
 Si el autor de llamada implementa el [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz (a través de [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` llevará a cabo dos pasos los metadatos para optimizar y comprimirlos directamente. En caso contrario, no se realizan optimizaciones.  
  
 Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas del momento de la importación. Este paso normalmente produce desplazamiento de registros, con el inconveniente de que se invalidan los tokens retenidos por la herramienta para futuras referencias. Los metadatos no informe al llamador de estos cambios en los tokens hasta después del segundo paso, sin embargo. En el segundo paso, se realizan varias optimizaciones que están diseñados para reducir el tamaño total de los metadatos, como la optimización de la ubicación (enlace temprano) `mdTypeRef` y `mdMemberRef` tokens cuando la referencia es un tipo o miembro que se declara en el ámbito de metadatos actual. En esta fase, se produce otra ronda de asignación del token. Después de esta fase, el motor de metadatos notifica al llamador, a través de su `IMapToken` interfaz, de cualquiera puede cambiar los valores de token.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
