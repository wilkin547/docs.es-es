---
title: "IMetaDataEmit::DefineMethod (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fa136f5e6669e58ef709db5b53f538804cfcac2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod (Método)
Crea una definición para un método o una función global con la firma especificada y devuelve un token al que la definición de método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] El `mdTypedef` símbolo (token) de la interfaz primaria del método o clase primaria. Establecer `td` a `mdTokenNil`, si va a definir una función global.  
  
 `szName`  
 [in] Nombre del miembro en Unicode.  
  
 `dwMethodFlags`  
 [in] Un valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración que especifica los atributos del método o una función global.  
  
 `pvSigBlob`  
 [in] La firma del método. La firma se conserva tal como lo suministró. Si tiene que especificar información adicional para los parámetros, use la [SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) método.  
  
 `cbSigBlob`  
 [in] El recuento de bytes en `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] La dirección del código.  
  
 `dwImplFlags`  
 [in] Un valor de la [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración que especifica las características de implementación del método.  
  
 `pmd`  
 [out] El token de miembro.  
  
## <a name="remarks"></a>Comentarios  
 La API de metadatos garantiza que se conserven los métodos en el mismo orden que los emite el llamador para una determinada clase o interfaz envolvente, que se especifica en el `td` parámetro.  
  
 Información adicional sobre el uso de `DefineMethod` y configuración de parámetros determinada se indica a continuación.  
  
## <a name="slots-in-the-v-table"></a>Ranuras de la tabla v.  
 Para establecer las ranuras de v-table, el tiempo de ejecución usa las definiciones de método. En el caso donde una o varias ranuras deben omitirse, tales como para conservar la paridad con un diseño de interfaz COM, se define un método ficticio para ocupar la ranura o ranuras en v-table; establecer el `dwMethodFlags` a la `mdRTSpecialName` valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración y especifique el nombre como:  
  
 _VtblGap\<*SequenceNumber*>\<\_*recuentoDeRanuras*>  
  
 donde *SequenceNumber* es el número de secuencia del método y *recuentoDeRanuras* es el número de ranuras que se omiten en la v-table. Si *recuentoDeRanuras* es se omite, se supone que es 1. Estos métodos ficticios no son invocables desde código administrado o no administrado y cualquier intento de llamarlas desde código administrado o no administrado, genera una excepción. Su único propósito es ocupar espacio en la tabla v que el tiempo de ejecución genera para la integración de COM.  
  
## <a name="duplicate-methods"></a>Métodos duplicados  
 No debe definir métodos duplicados. Es decir, no debe llamar `DefineMethod` con un conjunto de duplicado de valores en el `td`, `wzName`, y `pvSig` parámetros. (Estos tres parámetros juntos definen el método de forma unívoca.). Sin embargo, puede utilizar un triple duplicado siempre que, para una de las definiciones de método, establezca la `mdPrivateScope` de bits en el `dwMethodFlags` parámetro. (El `mdPrivateScope` bits significa que el compilador no emitirá una referencia a esta definición de método.)  
  
## <a name="method-implementation-information"></a>Información de implementación de método  
 Obtener información sobre la implementación del método a menudo no se conoce en el momento en que se declara el método. Por lo tanto, no es necesario pasar valores en el `ulCodeRVA` y `dwImplFlags` parámetros cuando se llama a `DefineMethod`. Los valores que se pueden proporcionar más adelante mediante [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), según corresponda.  
  
 En algunas situaciones, como la invocación de plataforma (PInvoke) o escenarios de interoperabilidad COM, no se proporcionarán el cuerpo del método, y `ulCodeRVA` debe establecerse en cero. En estas situaciones, el método no se debe etiquetar como abstracto, porque el tiempo de ejecución buscará la implementación.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definir un método para PInvoke  
 Para que cada función no administrada que se llame a través de PInvoke, debe definir un método administrado que representa la función no administrada de destino. Para definir el método administrado, utilice `DefineMethod` con algunos de los parámetros establecidos en determinados valores, dependiendo de la forma en que se utiliza PInvoke:  
  
-   PInvoke verdadero - implica la invocación de un método no administrado externo que reside en una DLL no administrada.  
  
-   PInvoke local: implica la invocación de un método no administrado nativo que está incrustado en el módulo administrado actual.  
  
 En la tabla siguiente se indican los valores de parámetro.  
  
|Parámetro|Valores de PInvoke verdadero|Valores de PInvoke local|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Establecer `mdStatic`; desactive `mdSynchronized` y `mdAbstract`.|  
|`pvSigBlob`|Una válido common language runtime (CLR) firma de método con parámetros que son válidos los tipos administrados.|Una firma de método CLR válida con parámetros que son válidos los tipos administrados.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Establecer `miCil` y `miManaged`.|Establecer `miNative` y `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
