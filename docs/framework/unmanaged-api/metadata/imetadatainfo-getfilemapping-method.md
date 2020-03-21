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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175270"
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
 [fuera] Un puntero al inicio del archivo asignado.  
  
 `pcbData`  
 [fuera] El tamaño de la región asignada. Si `pdwMappingType` `fmFlat`es , este es el tamaño del archivo.  
  
 `pdwMappingType`  
 [fuera] Un [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica el tipo de asignación. La implementación actual de Common Language `fmFlat`Runtime (CLR) siempre devuelve . Otros valores se reservan para un uso futuro. Sin embargo, siempre debe comprobar el valor devuelto, ya que otros valores pueden estar habilitados en versiones futuras o versiones de servicio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|Se rellenan todas las salidas.|  
|`E_INVALIDARG`|NULL se pasó como un valor de argumento.|  
|`COR_E_NOTSUPPORTED`|La implementación de CLR no puede proporcionar información sobre la región de memoria. Esto puede deberse a los siguientes motivos:<br /><br /> - El ámbito de `ofWrite` metadatos `ofCopyMemory` se abrió con la marca o.<br />- El ámbito de `ofReadOnly` metadatos se abrió sin la marca.<br />- El [método IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) se usó para abrir solo la parte de metadatos del archivo.<br />- El archivo no es un archivo ejecutable portátil (PE). **Nota:**  Estas condiciones dependen de la implementación de CLR y es probable que se debiliten en versiones futuras de CLR.|  
  
## <a name="remarks"></a>Observaciones  
 La memoria `ppvData` a la que apunta es válida solo mientras el ámbito de metadatos subyacente esté abierto.  
  
 Para que este método funcione, al asignar los metadatos de un archivo en disco a la memoria mediante una `ofReadOnly` llamada a la `ofWrite` [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, debe especificar la marca y no debe especificar el o `ofCopyMemory` marca.  
  
 La elección del tipo de asignación de archivos para cada ámbito es específica de una implementación determinada de CLR. No puede ser establecido por el usuario. La implementación actual de `fmFlat` `pdwMappingType`CLR siempre se devuelve en , pero esto puede cambiar en versiones futuras de CLR o en futuras versiones de servicio de una versión determinada. Siempre debe comprobar el `pdwMappingType`valor devuelto en , porque diferentes tipos tendrán diferentes diseños y desplazamientos.  
  
 No se admite pasar NULL para cualquiera de los tres parámetros. El método `E_INVALIDARG`devuelve y no se rellena ninguna de las salidas. Ignorar el tipo de asignación o el tamaño de la región puede dar lugar a una terminación anormal del programa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataInfo (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping (Enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
