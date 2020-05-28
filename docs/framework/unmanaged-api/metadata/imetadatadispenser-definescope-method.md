---
title: IMetaDataDispenser::DefineScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 021ef8de602d6dd928f49e69e36f8d4a61425745
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008370"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope (Método)
Crea un nuevo área en la memoria en la que se pueden crear nuevos metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `rclsid`  
 de CLSID de la versión de las estructuras de metadatos que se van a crear. Este valor se debe CLSID_CorMetaDataRuntime para la versión de .NET Framework 2,0.  
  
 `dwCreateFlags`  
 de Marcas que especifican las opciones. Este valor debe ser cero para el .NET Framework 2,0.  
  
 `riid`  
 de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para crear los nuevos metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "Emit". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 `DefineScope`crea un conjunto de tablas de metadatos en memoria, genera un GUID único (identificador de versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulos para la unidad de compilación que se emite.  
  
 Puede adjuntar atributos al ámbito de metadatos en su totalidad mediante el método [IMetaDataEmit:: SetModuleProps (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) , según corresponda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
