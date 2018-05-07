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
ms.openlocfilehash: cfe600b54eb03a07ea01375355c5ff94190e5d9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption (Método)
Establece la opción especificada en un valor determinado para el ámbito de metadatos actual. La opción controla cómo se administran las llamadas al ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `optionId`  
 [in] Un puntero a un GUID que especifica la opción que puede establecer.  
  
 `pValue`  
 [in] Valor que se va a utilizar para establecer la opción. El tipo de este valor debe ser una variante del tipo de la opción especificada.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumera los GUID disponibles que el `optionId` parámetro puede apuntar a y los correspondientes valores válidos para el `pValue` parámetro.  
  
|GUID|Descripción|`pValue` Parámetro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controla qué elementos se comprueban los duplicados. Cada vez que se llama un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) método que crea un nuevo elemento, puede pedir al método para comprobar si el elemento ya existe en el ámbito actual. Por ejemplo, puede comprobar la existencia de `mdMethodDef` elementos; en este caso, cuando se llama a [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), comprobará que el método no existe ya en el ámbito actual. Esta comprobación utiliza la clave que identifica de forma única un método determinado: primario de tipo, nombre y firma.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumeración.|  
|MetaDataRefToDefCheck|Controles que hacen referencia a elementos se convierten en definiciones. De forma predeterminada, el motor de metadatos optimizará el código convirtiendo un elemento que se hace referencia a su definición si realmente se ha definido el elemento que se hace referencia en el ámbito actual.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumeración.|  
|MetaDataNotificationForTokenMovement|Controles de qué reasignaciones de tokens que se producen durante una combinación de metadatos generan devoluciones de llamada. Use la [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) método para establecer su [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumeración.|  
|MetaDataSetENC|Controla el comportamiento de editar y continuar (ENC). Solo un modo de comportamiento se puede establecer a la vez.|Debe ser una variante de tipo UI4 y debe contener un valor de la [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumeración. El valor no es una máscara de bits.|  
|MetaDataErrorIfEmitOutOfOrder|Controles de los que genera-fuera de servicio los errores generan devoluciones de llamada. Emisión de metadatos fuera de servicio no es grave; Sin embargo, si emite los metadatos en un orden que favorece el motor de metadatos, los metadatos son más compacto y, por tanto, se pueden buscar de forma más eficaz. Use la `IMetaDataEmit::SetHandler` método para establecer su [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interfaz.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumeración.|  
|MetaDataImportOption|Controla qué tipos de elementos que se eliminaron durante un ENC los recupera un enumerador.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorImportOptions (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumeración.|  
|MetaDataThreadSafetyOptions|Controla si el motor de metadatos obtiene bloqueos, lo que garantiza la seguridad de los subprocesos de lector/escritor. De forma predeterminada, el motor se da por supuesto que el acceso es un subproceso único por el llamador, por lo que se obtiene ningún bloqueo. Los clientes son responsables de mantener la sincronización de subprocesos adecuada cuando se usa la API de metadatos.|Debe ser una variante de tipo UI4 y debe contener un valor de la [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumeración. El valor no es una máscara de bits.|  
|MetaDataGenerateTCEAdapters|Controla si el importador de la biblioteca de tipos debería generar los adaptadores de evento herméticamente acoplados (TCE) para los contenedores de punto de conexión COM.|Debe ser una variante de tipo BOOL. Si `pValue` se establece en `true`, el importador de la biblioteca de tipos genera los adaptadores TCE.|  
|MetaDataTypeLibImportNamespace|Especifica un espacio de nombres no predeterminado para la biblioteca de tipos que se va a importar.|Debe ser un valor null o una variante de tipo BSTR. Si `pValue` es un valor null, el espacio de nombres actual se establece en null; en caso contrario, el espacio de nombres actual se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataLinkerOptions|Controla si el vinculador debe generar un ensamblado o un archivo de módulo de .NET Framework.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumeración.|  
|MetaDataRuntimeVersion|Especifica la versión de common language runtime con la que se compiló esta imagen. La versión se almacena como una cadena, como "v1.0.3705".|Debe ser un valor nulo, un valor VT_EMPTY o una variante de tipo BSTR. Si `pValue` es null, la versión en tiempo de ejecución se establece en null. Si `pValue` es VT_EMPTY, la versión se establece en un valor predeterminado, que se dibuja desde la versión de Mscorwks.dll dentro del cual se ejecuta el código de metadatos. En caso contrario, la versión en tiempo de ejecución se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataMergerOptions|Especifica las opciones para la combinación de metadatos.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la `MergeFlags` enumeración, que se describe en el archivo CorHdr.h.|  
|MetaDataPreserveLocalRefs|Deshabilita la optimización locales referencias a definiciones.|Debe contener una combinación de los valores de la [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumeración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
