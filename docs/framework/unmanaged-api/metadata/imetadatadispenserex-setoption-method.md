---
title: IMetaDataDispenserEx::SetOption (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9e9d7a66f37759e6f62ddae2c5af989cee57e3b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470655"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption (Método)
Establece la opción especificada en un valor especificado para el ámbito de metadatos actual. La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `optionId`  
 [in] Un puntero a un GUID que especifica la opción debe establecerse.  
  
 `pValue`  
 [in] El valor que se usará para establecer la opción. El tipo de este valor debe ser una variante de tipo de la opción especificada.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumera los GUID disponibles que el `optionId` parámetro puede apuntar a y los correspondientes valores válidos para el `pValue` parámetro.  
  
|GUID|Descripción|`pValue` Parámetro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controla qué elementos se comprueban los duplicados. Cada vez que se llama una [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) método que crea un nuevo elemento, puede pedir el método para comprobar si el elemento ya existe en el ámbito actual. Por ejemplo, puede comprobar la existencia de `mdMethodDef` elementos; en este caso, cuando se llama a [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), comprobará que el método no existe ya en el ámbito actual. Esta comprobación usa la clave que identifica un método determinado: primario de tipo, nombre y firma.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumeración.|  
|MetaDataRefToDefCheck|Los controles que hacen referencia a elementos se convierten en definiciones. De forma predeterminada, el motor de metadatos optimizará el código mediante la conversión de un elemento que se hace referencia a su definición si el elemento que se hace referencia realmente está definido en el ámbito actual.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumeración.|  
|MetaDataNotificationForTokenMovement|Controles qué reasignaciones de tokens que se producen durante una combinación de metadatos generan devoluciones de llamada. Use la [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) método para establecer su [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumeración.|  
|MetaDataSetENC|Controla el comportamiento de editar y continuar (ENC). Solo un modo de comportamiento se puede establecer a la vez.|Debe ser una variante de tipo UI4 y debe contener un valor de la [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumeración. El valor no es una máscara de bits.|  
|MetaDataErrorIfEmitOutOfOrder|Controla qué errores emitidos-fuera de secuencia generan devoluciones de llamada. Emisión de metadatos fuera de servicio no es grave; Sin embargo, si emite los metadatos en un orden que favorece el motor de metadatos, los metadatos son más compacto y, por tanto, se pueden buscar más eficazmente. Use la `IMetaDataEmit::SetHandler` método para establecer su [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interfaz.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumeración.|  
|MetaDataImportOption|Controla qué tipos de elementos que se eliminaron durante un ENC los recupera un enumerador.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorImportOptions (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumeración.|  
|MetaDataThreadSafetyOptions|Controla si el motor de metadatos obtiene lector/escritor bloqueos, lo que garantiza la seguridad para subprocesos. De forma predeterminada, el motor se da por supuesto que acceso tiene un único subproceso del llamador, por lo que se obtiene ningún bloqueo. Los clientes son responsables de mantener la sincronización de subproceso correcta al usar la API de metadatos.|Debe ser una variante de tipo UI4 y debe contener un valor de la [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumeración. El valor no es una máscara de bits.|  
|MetaDataGenerateTCEAdapters|Controla si el importador de la biblioteca de tipos debe generar los adaptadores de evento estrechamente acopladas (TCE) para los contenedores de punto de conexión COM.|Debe ser una variante de tipo BOOL. Si `pValue` está establecido en `true`, los adaptadores de TCE genera el importador de la biblioteca de tipos.|  
|MetaDataTypeLibImportNamespace|Especifica un espacio de nombres no predeterminado para la biblioteca de tipos que se va a importar.|Debe ser un valor null o una variante de tipo BSTR. Si `pValue` es un valor null, el espacio de nombres actual se establece en null; en caso contrario, el espacio de nombres actual se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataLinkerOptions|Controla si el vinculador debe generar un ensamblado o un archivo de módulo de .NET Framework.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumeración.|  
|MetaDataRuntimeVersion|Especifica la versión de common language runtime para la que se compiló esta imagen. La versión se almacena como una cadena, como "v1.0.3705".|Debe ser un valor nulo, un valor VT_EMPTY o una variante de tipo BSTR. Si `pValue` es null, la versión en tiempo de ejecución se establece en null. Si `pValue` es VT_EMPTY, la versión se establece en un valor predeterminado, que se dibuja desde la versión de Mscorwks.dll dentro del cual se ejecuta el código de metadatos. En caso contrario, la versión en tiempo de ejecución se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataMergerOptions|Especifica opciones para combinar los metadatos.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la `MergeFlags` enumeración, que se describe en el archivo CorHdr.h.|  
|MetaDataPreserveLocalRefs|Deshabilita la optimización de referencias locales en las definiciones.|Debe contener una combinación de los valores de la [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumeración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
