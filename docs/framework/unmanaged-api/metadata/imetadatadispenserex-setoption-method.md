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
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175907"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption (Método)
Establece la opción especificada en un valor determinado para el ámbito de metadatos actual. La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `optionId`  
 [en] Puntero a un GUID que especifica la opción que se va a establecer.  
  
 `pValue`  
 [en] El valor que se va a utilizar para establecer la opción. El tipo de este valor debe ser una variante del tipo de la opción especificada.  
  
## <a name="remarks"></a>Observaciones  
 En la tabla siguiente se enumeran `optionId` los GUID disponibles a los `pValue` que puede apuntar el parámetro y los valores válidos correspondientes para el parámetro.  
  
|GUID|Descripción|`pValue`Parámetro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controla qué elementos se comprueban en busca de duplicados. Cada vez que se llama a un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) método que crea un nuevo elemento, puede pedir al método para comprobar si el elemento ya existe en el ámbito actual. Por ejemplo, puede comprobar la `mdMethodDef` existencia de elementos; en este caso, cuando se llama a [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), comprobará que el método no existe ya en el ámbito actual. Esta comprobación utiliza la clave que identifica de forma única un método determinado: tipo primario, nombre y firma.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [corCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumeración.|  
|MetaDataRefToDefCheck|Los controles que hacen referencia a elementos se convierten en definiciones. De forma predeterminada, el motor de metadatos optimizará el código convirtiendo un elemento al que se hace referencia a su definición si el elemento al que se hace referencia se define realmente en el ámbito actual.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [CorRefToDefCheck.](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)|  
|MetaDataNotificationForTokenMovement|Los controles que los reasignaciones de tokens que se producen durante una combinación de metadatos generan devoluciones de llamada. Utilice el método [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) para establecer la interfaz [IMapToken.](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [corNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumeración.|  
|MetaDataSetENC|Controla el comportamiento de editar y continuar (ENC). Solo se puede establecer un modo de comportamiento a la vez.|Debe ser una variante de tipo UI4 y debe contener un valor de la enumeración [CorSetENC.](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) El valor no es una máscara de bits.|  
|MetaDataErrorifemitOutofOrder|Controles que los errores emitidos fuera de orden generan devoluciones de llamada. La emisión de metadatos fuera de orden no es fatal; sin embargo, si emite metadatos en un orden que es favorecido por el motor de metadatos, los metadatos son más compactos y, por lo tanto, se pueden buscar de forma más eficaz. Utilice `IMetaDataEmit::SetHandler` el método para establecer la interfaz [IMetaDataError.](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [corErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumeración.|  
|MetaDataImportOption|Controla qué tipos de elementos que se eliminaron durante un ENC se recuperan mediante un enumerador.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [enumeración CorImportOptions Enumeration.](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)|  
|MetaDataThreadSafetyOptions|Controla si el motor de metadatos obtiene bloqueos de lector/escritor, lo que garantiza la seguridad de los subprocesos. De forma predeterminada, el motor supone que el autor de la llamada tiene un solo subproceso, por lo que no se obtieneningún ningún bloqueo. Los clientes son responsables de mantener la sincronización de subprocesos adecuada al usar la API de metadatos.|Debe ser una variante de tipo UI4 y debe contener un valor de la [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumeración. El valor no es una máscara de bits.|  
|MetaDataGenerateTCEAdapters|Controla si el importador de biblioteca de tipos debe generar los adaptadores de eventos acoplados estrechamente (TCE) para contenedores de punto de conexión COM.|Debe ser una variante del tipo BOOL. Si `pValue` se `true`establece en , el importador de biblioteca de tipos genera los adaptadores TCE.|  
|MetaDataTypeLibImportNamespace|Especifica un espacio de nombres no predeterminado para la biblioteca de tipos que se está importando.|Debe ser un valor nulo o una variante de tipo BSTR. Si `pValue` es un valor nulo, el espacio de nombres actual se establece en null; de lo contrario, el espacio de nombres actual se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataLinkerOptions|Controla si el vinculador debe generar un ensamblado o un archivo de módulo de .NET Framework.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la [corLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumeración.|  
|MetaDataRuntimeVersion|Especifica la versión de Common Language Runtime en la que se creó esta imagen. La versión se almacena como una cadena, como "v1.0.3705".|Debe ser un valor nulo, un valor VT_EMPTY o una variante de tipo BSTR. Si `pValue` es null, la versión en tiempo de ejecución se establece en null. Si `pValue` se VT_EMPTY, la versión se establece en un valor predeterminado, que se extrae de la versión de Mscorwks.dll dentro de la cual se ejecuta el código de metadatos. De lo contrario, la versión en tiempo de ejecución se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataMergerOptions|Especifica las opciones para combinar metadatos.|Debe ser una variante de tipo UI4 y debe `MergeFlags` contener una combinación de los valores de la enumeración, que se describe en el archivo CorHdr.h.|  
|MetaDataPreserveLocalRefs|Deshabilita la optimización de referencias locales en definiciones.|Debe contener una combinación de los valores de la [corLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumeración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataDispenserEx (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
