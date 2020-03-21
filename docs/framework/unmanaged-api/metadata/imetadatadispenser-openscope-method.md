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
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175946"
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
 [en] El nombre del archivo que se va a abrir. El archivo debe contener metadatos de Common Language Runtime (CLR).  
  
 `dwOpenFlags`  
 [en] Valor de la enumeración [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para la apertura.  
  
 `riid`  
 [en] El IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada utilizará la interfaz para importar (leer) o emitir (escribir) metadatos.  
  
 El valor `riid` de debe especificar una de las interfaces "import" o "emit". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [fuera] El puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Observaciones  
 La copia en memoria de los metadatos se puede consultar mediante métodos de una de las interfaces de "importación" o agregarse a métodos de uso de una de las interfaces "emitir".  
  
 Si el archivo de destino no `OpenScope` contiene metadatos CLR, se producirá un error en el método.  
  
 En la versión 1.0 y 1.1 de .NET `dwOpenFlags` Framework, si se abre un ámbito con el conjunto de read, es apto para compartir. Es decir, si `OpenScope` las llamadas posteriores para pasar el nombre de un archivo que se abrió anteriormente, el ámbito existente se reutiliza y no se crea un nuevo conjunto de estructuras de datos. Sin embargo, pueden surgir problemas debido a este uso compartido.  
  
 En la versión 2.0 de .NET Framework, los ámbitos abiertos con `dwOpenFlags` set en ofRead ya no se comparten. Utilice el valor ofReadOnly para permitir que se comparta el ámbito. Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
