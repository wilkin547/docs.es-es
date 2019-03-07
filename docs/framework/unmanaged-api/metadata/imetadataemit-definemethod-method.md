---
title: IMetaDataEmit::DefineMethod (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2372aac00473786df9b5deefb969fc02abd8daa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496111"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod (Método)
Crea una definición para un método o una función global con la firma especificada y devuelve un token para esa definición de método.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `td`  
 [in] El `mdTypedef` símbolo (token) de la interfaz primaria del método o clase primaria. Establecer `td` a `mdTokenNil`, si está definiendo una función global.  
  
 `szName`  
 [in] El nombre del miembro en Unicode.  
  
 `dwMethodFlags`  
 [in] Un valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración que especifica los atributos del método o función global.  
  
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
  
 Información adicional sobre el uso de `DefineMethod` y configuración de los parámetros se indican a continuación.  
  
## <a name="slots-in-the-v-table"></a>Ranuras de la tabla v.  
 El tiempo de ejecución usa las definiciones de método para configurar ranuras de v-table. En el caso donde uno o más espacios deben omitirse, tales como para conservar la paridad con un diseño de interfaz COM, se define un método ficticio para ocupar la ranura o ranuras en la tabla v; establecer el `dwMethodFlags` a la `mdRTSpecialName` valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración y especifique el nombre como:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 donde *SequenceNumber* es el número de secuencia del método y *recuentoDeRanuras* es el número de ranuras que se omiten en la tabla v. Si *recuentoDeRanuras* es se omite, se asume 1. Estos métodos ficticios no son invocables desde código administrado o no administrado y cualquier intento de llamarlas desde código administrado o no administrado, genera una excepción. Su único objetivo es ocupan espacio en la tabla v que genera el tiempo de ejecución para la integración de COM.  
  
## <a name="duplicate-methods"></a>Métodos duplicados  
 No debería definir métodos duplicados. Es decir, no debería llamar `DefineMethod` con un conjunto duplicado de valores en el `td`, `wzName`, y `pvSig` parámetros. (Estos tres parámetros juntos definen el método de forma unívoca.). Sin embargo, puede utilizar un triple duplicado siempre que uno de las definiciones de método, Establece el `mdPrivateScope` bit en el `dwMethodFlags` parámetro. (El `mdPrivateScope` bit significa que el compilador no emitirá una referencia a esta definición de método.)  
  
## <a name="method-implementation-information"></a>Información de método de implementación  
 A menudo no se conoce la información sobre la implementación del método en el momento en que se declara el método. Por lo tanto, no es necesario pasar valores en el `ulCodeRVA` y `dwImplFlags` parámetros cuando se llama a `DefineMethod`. Se pueden proporcionar los valores más adelante a través [SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), según corresponda.  
  
 En algunas situaciones, como la invocación de plataforma (PInvoke) o escenarios de interoperabilidad COM, no se proporcionarán el cuerpo del método, y `ulCodeRVA` debe establecerse en cero. En estas situaciones, el método no debe etiquetar como abstracto, porque el tiempo de ejecución buscará la implementación.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definir un método para PInvoke  
 Para que cada función no administrada que se llame a través de PInvoke, debe definir un método administrado que representa la función no administrada de destino. Para definir el método administrado, utilice `DefineMethod` con algunos de los parámetros establecidos a ciertos valores, dependiendo de la forma en que se utiliza PInvoke:  
  
-   PInvoke verdadero - implica la invocación de un método no administrado externo que reside en una DLL no administrada.  
  
-   PInvoke local: implica la invocación de un método nativo no administrado que está incrustado en el módulo administrado actual.  
  
 La configuración de parámetros se proporciona en la tabla siguiente.  
  
|Parámetro|Valores de PInvoke verdadero|Valores de PInvoke local|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Establecer `mdStatic`; desactive `mdSynchronized` y `mdAbstract`.|  
|`pvSigBlob`|Tipos administrados de una common language runtime (CLR) firma de método válida con parámetros que son válidos.|Una firma de método CLR válida con parámetros que son válidos los tipos administrados.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Establecer `miCil` y `miManaged`.|Establecer `miNative` y `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
