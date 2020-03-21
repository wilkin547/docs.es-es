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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177672"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod (Método)
Crea una definición para un método o una función global con la firma especificada y devuelve un token a esa definición de método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 [en] El `mdTypedef` token de la clase primaria o la interfaz primaria del método. Establézalo `td` en `mdTokenNil`, si está definiendo una función global.  
  
 `szName`  
 [en] El nombre del miembro en Unicode.  
  
 `dwMethodFlags`  
 [en] Valor de la enumeración [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) que especifica los atributos del método o función global.  
  
 `pvSigBlob`  
 [en] La firma del método. La firma se conserva como se proporciona. Si necesita especificar información adicional para cualquier parámetro, utilice el [Método IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 [en] El recuento de `pvSigBlob`bytes en .  
  
 `ulCodeRVA`  
 [en] La dirección del código.  
  
 `dwImplFlags`  
 [en] Valor de la enumeración [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) que especifica las características de implementación del método.  
  
 `pmd`  
 [fuera] El token de miembro.  
  
## <a name="remarks"></a>Observaciones  
 La API de metadatos garantiza conservar los métodos en el mismo orden en que el autor `td` de la llamada los emite para una clase o interfaz envolvente determinada, que se especifica en el parámetro.  
  
 A continuación se `DefineMethod` proporciona información adicional sobre el uso y la configuración de parámetros particulares.  
  
## <a name="slots-in-the-v-table"></a>Ranuras en la tabla V  
 El tiempo de ejecución utiliza definiciones de método para configurar ranuras de tabla v. En el caso en que uno o más slots necesitan ser omitidos, tales como para preservar la paridad con un diseño de interfaz COM, se define un método ficticio para tomar el slot o los slots en la tabla v; establezca `dwMethodFlags` el `mdRTSpecialName` valor de la enumeración [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) y especifique el nombre como:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 donde *SequenceNumber* es el número de secuencia del método y *CountOfSlots* es el número de ranuras que se deben omitir en la tabla v. Si se omite *CountOfSlots,* se asume 1. Estos métodos ficticios no se pueden llamar desde código administrado o no administrado y cualquier intento de llamarlos, desde código administrado o no administrado, genera una excepción. Su único propósito es ocupar espacio en la tabla v que genera el tiempo de ejecución para la integración COM.  
  
## <a name="duplicate-methods"></a>Métodos duplicados  
 No debe definir métodos duplicados. Es decir, no `DefineMethod` debe llamar con un `td`conjunto `wzName`duplicado `pvSig` de valores en los parámetros , , y . (Estos tres parámetros juntos definen de forma única el método.). Sin embargo, puede usar un triple duplicado siempre que, para `mdPrivateScope` una `dwMethodFlags` de las definiciones de método, establezca el bit en el parámetro. (El `mdPrivateScope` bit significa que el compilador no emitirá una referencia a esta definición de método.)  
  
## <a name="method-implementation-information"></a>Información de implementación del método  
 La información sobre la implementación del método a menudo no se conoce en el momento en que se declara el método. Por lo tanto, no es `ulCodeRVA` necesario `dwImplFlags` pasar `DefineMethod`valores en los parámetros y al llamar a . Los valores se pueden proporcionar más adelante a través de [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), según corresponda.  
  
 En algunas situaciones, como la invocación de plataforma (PInvoke) o escenarios de interoperabilidad COM, el cuerpo del método no se proporcionará y `ulCodeRVA` debe establecerse en cero. En estas situaciones, el método no debe etiquetarse como abstracto, porque el tiempo de ejecución localizará la implementación.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definición de un método para PInvoke  
 Para llamar a cada función no administrada a través de PInvoke, debe definir un método administrado que represente la función no administrada de destino. Para definir el método `DefineMethod` administrado, utilice con algunos de los parámetros establecidos en determinados valores, dependiendo de la forma en que se utilice PInvoke:  
  
- True PInvoke: implica la invocación de un método no administrado externo que reside en un archivo DLL no administrado.  
  
- PInvoke local: implica la invocación de un método no administrado nativo que está incrustado en el módulo administrado actual.  
  
 La configuración de los parámetros se indica en la tabla siguiente.  
  
|Parámetro|Valores para true PInvoke|Valores para PInvoke local|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Establecer `mdStatic`; claro `mdSynchronized` `mdAbstract`y .|  
|`pvSigBlob`|Una firma de método de Common Language Runtime (CLR) válida con parámetros que son tipos administrados válidos.|Una firma de método CLR válida con parámetros que son tipos administrados válidos.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Establezca `miCil` y `miManaged`.|Establezca `miNative` y `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
