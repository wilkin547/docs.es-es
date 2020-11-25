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
ms.openlocfilehash: f2a85bafc3e2f25b2ed6116a46a9938d869dbaae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726085"
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
 de Un valor de la enumeración [CorOpenFlags (](coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.  
  
 `riid`  
 de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.  
  
 El valor de `riid` debe especificar una de las interfaces "Import" o "Emit". Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  

 La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".  
  
 Si el archivo de destino no contiene metadatos de CLR, `OpenScope` se producirá un error en el método.  
  
 En la .NET Framework versión 1,0 y la versión 1,1, si se abre un ámbito con `dwOpenFlags` establecido en ' Read ', es válido para el uso compartido. Es decir, si las llamadas posteriores para `OpenScope` pasar el nombre de un archivo que se ha abierto anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos. Sin embargo, pueden surgir problemas debido a este uso compartido.  
  
 En la versión 2,0 de .NET Framework, los ámbitos abiertos con `dwOpenFlags` establecido en he leído ya no se comparten. Use el valor ofReadOnly para permitir que se comparta el ámbito. Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
