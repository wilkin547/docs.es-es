---
title: "IMetaDataEmit::GetSaveSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9686e8e2c4e8276e725852cb58fac7ed1973778b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize (Método)
Obtiene el tamaño binario estimado del ensamblado y sus metadatos en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `fSave`  
 [in] Un valor de la [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeración que especifica si se debe obtener un tamaño exacta o aproximado. Sólo hay tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:  
  
-   cssAccurate devuelve el tamaño de almacenamiento exacto, pero tarda más tiempo en calcular.  
  
-   cssQuick devuelve un tamaño con relleno por motivos de seguridad, pero necesita menos tiempo para calcular.  
  
-   cssDiscardTransientCAs indica a `GetSaveSize` que puede producir varios atributos personalizados descartables inmediatamente.  
  
 `pdwSaveSize`  
 [out] Un puntero al tamaño que es necesario para guardar el archivo.  
  
## <a name="remarks"></a>Comentarios  
 `GetSaveSize`calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual. (Una llamada a la [SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) método emitiría este número de bytes.)  
  
 Si el llamador implementa la [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz (a través de [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` llevará a cabo dos pasos los metadatos para optimizar y comprimirlos directamente. En caso contrario, no se realizan optimizaciones.  
  
 Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas del momento de la importación. Este paso normalmente como resultado de desplazamiento de registros, con el inconveniente que dejan de símbolos (tokens) retenidos por la herramienta para futuras referencias. Los metadatos no informar al llamador de estos cambios en los símbolos hasta después del segundo paso, sin embargo. En el segundo paso, se realizan varias optimizaciones que están diseñados para reducir el tamaño total de los metadatos, como optimizar alejado (enlace temprano) `mdTypeRef` y `mdMemberRef` tokens cuando la referencia es un tipo o miembro que se declara en el ámbito de metadatos actual. En esta fase, se produce otra ronda de asignación de símbolo (token). Después de esta fase, el motor de metadatos notifica al llamador, a través de su `IMapToken` cambiará de interfaz, de los valores de token.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
