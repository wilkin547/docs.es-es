---
title: IMetaDataInfo::GetFileMapping (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b45d78548f2b1a7e17f61c5228cd68f228fe4980
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478879"
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
  
## <a name="parameters"></a>Parámetros  
 `ppvData`  
 [out] Un puntero al principio del archivo asignado.  
  
 `pcbData`  
 [out] El tamaño de la región asignada. Si `pdwMappingType` es `fmFlat`, este es el tamaño del archivo.  
  
 `pdwMappingType`  
 [out] Un [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica el tipo de asignación. La implementación actual de common language runtime (CLR) siempre devuelve `fmFlat`. Otros valores están reservados para uso futuro. Sin embargo, debe comprobar siempre el valor devuelto, porque pueden habilitarse en versiones futuras de otros valores o las versiones de servicio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|Se rellenan todos los resultados.|  
|`E_INVALIDARG`|Se pasa NULL como un valor de argumento.|  
|`COR_E_NOTSUPPORTED`|La implementación de CLR no puede proporcionar información acerca de la región de memoria. Esto puede ocurrir por las razones siguientes:<br /><br /> -El ámbito de metadatos se abrió con la `ofWrite` o `ofCopyMemory` marca.<br />-El ámbito de metadatos se abrió sin la `ofReadOnly` marca.<br />-El [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) usó el método para abrir solo la parte de metadatos del archivo.<br />-El archivo no es un archivo ejecutable portable (PE). **Nota:**  Estas condiciones dependen de la implementación de CLR y están probables que se debiliten en futuras versiones de CLR.|  
  
## <a name="remarks"></a>Comentarios  
 La memoria que `ppvData` apunta a es válido solo mientras está abierto el ámbito de metadatos subyacente.  
  
 Para este método funcione, al asignar los metadatos de un archivo en disco en la memoria mediante una llamada a la [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, debe especificar el `ofReadOnly` marca y no debe especificar el `ofWrite` o `ofCopyMemory` marca.  
  
 La elección del tipo de asignación de archivo para cada ámbito es específica para una implementación determinada de CLR. No se puede establecer por el usuario. La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType`, pero esto puede cambiar en futuras versiones de CLR o en futuras versiones de servicio de una versión concreta. Siempre debe comprobar el valor devuelto `pdwMappingType`, ya que tendrán diferentes tipos distintos diseños y desplazamientos.  
  
 No se admite pasar NULL para cualquiera de los tres parámetros. El método devuelve `E_INVALIDARG`, y ninguna de las salidas se rellenan. Se omite el tipo de asignación o el tamaño de la región puede provocar la terminación anómala del programa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataInfo (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
