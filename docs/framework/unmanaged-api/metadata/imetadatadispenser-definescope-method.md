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
ms.openlocfilehash: 381c38542dcde242c0a1a4e71e9b99316328159d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436237"
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
 `DefineScope` crea un conjunto de tablas de metadatos en memoria, genera un GUID único (identificador de versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulos para la unidad de compilación que se emite.  
  
 Puede adjuntar atributos al ámbito de metadatos en su totalidad mediante el método [IMetaDataEmit:: SetModuleProps (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) , según corresponda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
