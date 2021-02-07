---
description: 'Más información sobre: IMetaDataInfo:: Getfilemapping ((método)'
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
ms.openlocfilehash: 82a1a23c50a4d8340804f66966933fc6a11e0f8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688486"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping (Método)

Obtiene la región de memoria del archivo asignado y el tipo de asignación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppvData`  
 enuncia Puntero al principio del archivo asignado.  
  
 `pcbData`  
 enuncia Tamaño de la región asignada. Si `pdwMappingType` es `fmFlat` , es el tamaño del archivo.  
  
 `pdwMappingType`  
 enuncia Valor de [corfilemapping (](corfilemapping-enumeration.md) que indica el tipo de asignación. La implementación actual del Common Language Runtime (CLR) siempre devuelve `fmFlat` . Otros valores se reservan para un uso futuro. Sin embargo, siempre debe comprobar el valor devuelto, ya que otros valores pueden estar habilitados en versiones futuras o versiones de servicio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|Se rellenan todas las salidas.|  
|`E_INVALIDARG`|Se pasó NULL como un valor de argumento.|  
|`COR_E_NOTSUPPORTED`|La implementación de CLR no puede proporcionar información sobre la región de memoria. Esto puede deberse a los siguientes motivos:<br /><br /> -El ámbito de metadatos se abrió con la `ofWrite` `ofCopyMemory` marca o.<br />-El ámbito de metadatos se abrió sin la `ofReadOnly` marca.<br />-El método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) se usó para abrir solo la parte de metadatos del archivo.<br />-El archivo no es un archivo ejecutable portable (PE). **Nota:**  Estas condiciones dependen de la implementación de CLR y es probable que se debiliten en versiones futuras de CLR.|  
  
## <a name="remarks"></a>Observaciones  

 La memoria a la que `ppvData` apunta solo es válida siempre y cuando el ámbito de los metadatos subyacentes sea abierto.  
  
 Para que este método funcione, cuando asigne los metadatos de un archivo en disco a la memoria mediante una llamada al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , debe especificar la `ofReadOnly` marca y no debe especificar la `ofWrite` `ofCopyMemory` marca o.  
  
 La elección del tipo de asignación de archivos para cada ámbito es específica de una implementación determinada de CLR. El usuario no puede establecerlo. La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType` , pero puede cambiar en versiones futuras de CLR o en futuras versiones de servicio de una versión determinada. Siempre debe comprobar el valor devuelto en `pdwMappingType` , porque los distintos tipos tendrán distintos diseños y desplazamientos.  
  
 No se admite pasar NULL para ninguno de los tres parámetros. El método devuelve `E_INVALIDARG` y no se rellena ninguna de las salidas. Si se omite el tipo de asignación o el tamaño de la región, se puede producir una terminación anómala del programa.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataInfo (Interfaz)](imetadatainfo-interface.md)
- [CorFileMapping (Enumeración)](corfilemapping-enumeration.md)
