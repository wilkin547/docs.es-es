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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b94987631f7dbbe39e585a8ea2c2252b9427613
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079609"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope (Método)
Se abre un archivo existente, en el disco y asigna sus metadatos en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szScope`  
 [in] El nombre del archivo que se puede abrir. El archivo debe contener metadatos de common language runtime (CLR).  
  
 `dwOpenFlags`  
 [in] Un valor de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeración para especificar el modo (leer, escribir etc.) para abrir.  
  
 `riid`  
 [in] El IID de la interfaz de metadatos deseados va a devolver; el llamador utilizará la interfaz de importación (lectura) o emitir metadatos (escritura).  
  
 El valor de `riid` debe especificar una de las interfaces de "importación" o "emite". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 La copia en memoria de los metadatos se puede consultar con los métodos de una de las interfaces de "importación" o agregado a métodos de una de las interfaces "emite".  
  
 Si el archivo de destino no contiene metadatos de CLR, el `OpenScope` método generará un error.  
  
 En .NET Framework versiones 1.0 y 1.1, si un ámbito se abre con `dwOpenFlags` se establece en ofRead, es apto para el uso compartido. Es decir, si posteriores llamadas a `OpenScope` pase el nombre de un archivo que se abrió anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos. Sin embargo, pueden surgir problemas debido a este uso compartido.  
  
 En la versión 2.0 de .NET Framework, los ámbitos abierto con `dwOpenFlags` establecido en ofRead ya no se comparten. Use el valor ofReadOnly para permitir que el ámbito para compartirse. Cuando se comparte un ámbito, se producirá un error en las consultas que usan "lectura/escritura" interfaces de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenser (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
