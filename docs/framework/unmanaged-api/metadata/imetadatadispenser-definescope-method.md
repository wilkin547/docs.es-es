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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1763f9341af2d90cf465cb554bf7f282a4d92058
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777813"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope (Método)
Crea una nueva área de memoria en el que puede crear nuevos metadatos.  
  
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
 [in] El CLSID de la versión de las estructuras de metadatos que se va a crear. Este valor debe ser CLSID_CorMetaDataRuntime para la versión 2.0 de .NET Framework.  
  
 `dwCreateFlags`  
 [in] Marcadores que especifican opciones. Este valor debe ser cero para .NET Framework 2.0.  
  
 `riid`  
 [in] El IID de la interfaz de metadatos deseados va a devolver; el llamador utilizará la interfaz para crear los nuevos metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "emite". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 `DefineScope` crea un conjunto de tablas de metadatos en memoria, genera un único GUID (identificador de la versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulo para la unidad de compilación que se emiten.  
  
 Puede asociar los atributos para el ámbito de metadatos como un todo usando el [SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) método, según corresponda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
