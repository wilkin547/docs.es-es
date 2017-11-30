---
title: "IMetaDataInfo::GetFileMapping (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74f44d366ec4f3848f7c8436e208dcaee3466fe1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping (Método)
Obtiene la región de memoria del archivo asignado y el tipo de asignación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppvData`  
 [out] Un puntero al principio del archivo asignado.  
  
 `pcbData`  
 [out] El tamaño de la región asignada. Si `pdwMappingType` es `fmFlat`, este es el tamaño del archivo.  
  
 `pdwMappingType`  
 [out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica el tipo de asignación. La implementación actual de common language runtime (CLR) siempre devuelve `fmFlat`. Otros valores se reservan para uso futuro. Sin embargo, siempre debe comprobar el valor devuelto, porque otros valores pueden habilitarse en versiones futuras o actualizaciones service Release.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|Todas las salidas se llenan.|  
|`E_INVALIDARG`|Se pasó NULL como un valor de argumento.|  
|`COR_E_NOTSUPPORTED`|La implementación de CLR no puede proporcionar información acerca de la región de memoria. Esto puede ocurrir por las razones siguientes:<br /><br /> -El ámbito de metadatos se abrió con la `ofWrite` o `ofCopyMemory` marca.<br />-El ámbito de metadatos se abrió sin la `ofReadOnly` marca.<br />-El [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método utilizado para abrir solo la parte de metadatos del archivo.<br />-El archivo no es un archivo ejecutable portable (PE). **Nota:** estas condiciones dependen de la implementación de CLR y es probablemente debilita en futuras versiones de CLR.|  
  
## <a name="remarks"></a>Comentarios  
 La memoria que `ppvData` señala a es válido solo mientras está abierto el ámbito de metadatos subyacente.  
  
 En orden para que funcione, al asignar los metadatos de un archivo en disco en la memoria mediante una llamada a este método la [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, debe especificar el `ofReadOnly` marca y no debe especificar el `ofWrite` o `ofCopyMemory` marca.  
  
 La elección del tipo de asignación de archivo para cada ámbito es específica de una implementación determinada del CLR. El usuario no se puede establecer. La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType`, pero esto puede cambiar en futuras versiones de CLR o en futuras versiones del servicio de una versión concreta. Siempre debe comprobar el valor devuelto `pdwMappingType`, porque tipos diferentes tendrán diseños y desplazamientos.  
  
 No se admite pasar NULL para cualquiera de los tres parámetros. El método devuelve `E_INVALIDARG`, y ninguna de las salidas se llenan. Se omitirá el tipo de asignación o el tamaño de la región puede dar lugar a la terminación anómala del programa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataInfo (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [CorFileMapping (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
