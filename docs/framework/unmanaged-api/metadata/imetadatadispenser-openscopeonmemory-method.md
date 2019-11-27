---
title: IMetaDataDispenser::OpenScopeOnMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442310"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory (Método)
Abre un área de memoria que contiene los metadatos existentes. Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pData`  
 de Puntero que especifica la dirección de inicio del área de memoria.  
  
 `cbData`  
 de Tamaño del área de memoria, en bytes.  
  
 `dwOpenFlags`  
 de Un valor de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.  
  
 `riid`  
 de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "Import" o "Emit". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".  
  
 El método `OpenScopeOnMemory` es similar al método [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , con la excepción de que los metadatos de interés ya existen en la memoria, en lugar de en un archivo en disco.  
  
 Si el área de destino de la memoria no contiene metadatos de Common Language Runtime (CLR), se producirá un error en el método `OpenScopeOnMemory`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
