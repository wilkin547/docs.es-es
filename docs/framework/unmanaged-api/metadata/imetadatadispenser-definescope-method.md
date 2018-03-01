---
title: "IMetaDataDispenser::DefineScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: df7a700a5747f88f14cbfa4d10f1f4d0c2a14ab7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope (Método)
Crea una nueva área de memoria en el que puede crear nuevos metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `rclsid`  
 [in] El CLSID de la versión de estructuras de metadatos que se va a crear. Este valor debe ser CLSID_CorMetaDataRuntime para la versión 2.0 de .NET Framework.  
  
 `dwCreateFlags`  
 [in] Marcas que especifican opciones. Este valor debe ser cero para .NET Framework 2.0.  
  
 `riid`  
 [in] El IID de la interfaz de metadatos deseados devolverá; el llamador utilizará la interfaz para crear los nuevos metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "emite". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 `DefineScope`crea un conjunto de tablas de metadatos en memoria, genera un único GUID (identificador de la versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulo para la unidad de compilación que se va a emitir.  
  
 Puede asociar atributos al ámbito de metadatos como un conjunto mediante la [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) método, según corresponda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
