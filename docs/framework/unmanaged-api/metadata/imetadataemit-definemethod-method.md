---
description: 'Más información acerca de: IMetaDataEmit::D método efineMethod'
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
ms.openlocfilehash: b0ba2bb68f1d4387229767f6f2550d64b9008898
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677971"
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
 de `mdTypedef` Token de la clase primaria o interfaz primaria del método. `td`Se establece en `mdTokenNil` si se define una función global.  
  
 `szName`  
 de Nombre del miembro en Unicode.  
  
 `dwMethodFlags`  
 de Un valor de la enumeración [cormethodattr (](cormethodattr-enumeration.md) que especifica los atributos del método o la función global.  
  
 `pvSigBlob`  
 de La firma del método. La firma se conserva como se proporciona. Si necesita especificar información adicional para cualquier parámetro, use el método [IMetaDataEmit:: setparamprops (](imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 de Recuento de bytes de `pvSigBlob` .  
  
 `ulCodeRVA`  
 de Dirección del código.  
  
 `dwImplFlags`  
 de Un valor de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) que especifica las características de implementación del método.  
  
 `pmd`  
 enuncia El token de miembro.  
  
## <a name="remarks"></a>Observaciones  

 La API de metadatos garantiza la persistencia de los métodos en el mismo orden que el llamador los emite para una clase o interfaz envolvente determinada, que se especifica en el `td` parámetro.  
  
 A continuación se proporciona información adicional sobre el uso de `DefineMethod` y los valores de parámetros concretos.  
  
## <a name="slots-in-the-v-table"></a>Ranuras de la tabla V  

 El motor en tiempo de ejecución utiliza definiciones de método para configurar las ranuras de la tabla v. En el caso de que sea necesario omitir una o más ranuras, como conservar la paridad con un diseño de interfaz COM, se define un método ficticio para ocupar la ranura o las ranuras de la tabla v. establezca `dwMethodFlags` en el `mdRTSpecialName` valor de la enumeración [cormethodattr (](cormethodattr-enumeration.md) y especifique el nombre como:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 donde *SequenceNumber* es el número de secuencia del método y *CountOfSlots* es el número de ranuras que se van a omitir en la tabla v. Si se omite *CountOfSlots* , se asume 1. Estos métodos ficticios no son Invocables desde código administrado o no administrado, y cualquier intento de llamarlos, desde código administrado o no administrado, genera una excepción. Su única finalidad es ocupar espacio en la tabla v que el Runtime genera para la integración COM.  
  
## <a name="duplicate-methods"></a>Métodos duplicados  

 No debe definir métodos duplicados. Es decir, no debe llamar a `DefineMethod` con un conjunto duplicado de valores en `td` los `wzName` parámetros, y `pvSig` . (Estos tres parámetros juntos definen de forma única el método). Sin embargo, puede usar un triple duplicado, siempre y cuando, para una de las definiciones de método, establezca el `mdPrivateScope` bit en el `dwMethodFlags` parámetro. (El `mdPrivateScope` bit significa que el compilador no emitirá una referencia a esta definición de método).  
  
## <a name="method-implementation-information"></a>Información de implementación de método  

 A menudo, no se conoce la información sobre la implementación del método en el momento en que se declara el método. Por lo tanto, no es necesario pasar valores en los `ulCodeRVA` `dwImplFlags` parámetros y al llamar a `DefineMethod` . Los valores se pueden proporcionar más adelante a través de [IMetaDataEmit:: setmethodimplflags (](imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA (](imetadataemit-setrva-method.md), según corresponda.  
  
 En algunas situaciones, como los escenarios de invocación de plataforma (PInvoke) o de interoperabilidad COM, el cuerpo del método no se proporcionará y `ulCodeRVA` debe establecerse en cero. En estas situaciones, el método no debe etiquetarse como abstracto, porque el tiempo de ejecución buscará la implementación.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definir un método para PInvoke  

 Para cada función no administrada a la que se va a llamar a través de PInvoke, debe definir un método administrado que represente la función de destino no administrada. Para definir el método administrado, use `DefineMethod` con algunos de los parámetros establecidos en ciertos valores, dependiendo de la forma en que se utilice PInvoke:  
  
- True PInvoke: implica la invocación de un método externo no administrado que se encuentra en un archivo DLL no administrado.  
  
- PInvoke local: implica la invocación de un método nativo no administrado que está incrustado en el módulo administrado actual.  
  
 La configuración de parámetros se indica en la tabla siguiente.  
  
|Parámetro|Valores para PInvoke verdadero|Valores de PInvoke local|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Establezca `mdStatic` ; borre `mdSynchronized` y `mdAbstract` .|  
|`pvSigBlob`|Una firma de método Common Language Runtime (CLR) válida con parámetros que son tipos administrados válidos.|Firma de método CLR válida con parámetros que son tipos administrados válidos.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Establezca `miCil` y `miManaged`.|Establezca `miNative` y `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
