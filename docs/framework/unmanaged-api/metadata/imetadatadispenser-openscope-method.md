---
title: IMetaDataDispenser::OpenScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442328"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope (Método)
Abre un archivo en disco existente y asigna sus metadatos a la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szScope`  
 de Nombre del archivo que se va a abrir. El archivo debe contener metadatos de Common Language Runtime (CLR).  
  
 `dwOpenFlags`  
 de Un valor de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.  
  
 `riid`  
 de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "Import" o "Emit". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".  
  
 Si el archivo de destino no contiene metadatos de CLR, se producirá un error en el método `OpenScope`.  
  
 En el .NET Framework versión 1,0 y la versión 1,1, si se abre un ámbito con `dwOpenFlags` establecido en unread, es válido para el uso compartido. Es decir, si las llamadas subsiguientes a `OpenScope` pasan el nombre de un archivo que se abrió anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos. Sin embargo, pueden surgir problemas debido a este uso compartido.  
  
 En la versión .NET Framework 2,0, los ámbitos abiertos con `dwOpenFlags` establecido en unread ya no se comparten. Use el valor ofReadOnly para permitir que se comparta el ámbito. Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
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
