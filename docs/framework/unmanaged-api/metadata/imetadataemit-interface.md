---
description: 'Más información sobre: interfaz IMetaDataEmit'
title: IMetaDataEmit (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
ms.openlocfilehash: da8786f25e4081d3cc9c32cbb7ea7386d2e9f1f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745988"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit (Interfaz)

Proporciona métodos para crear, modificar y guardar metadatos acerca del ensamblado en el ámbito definido actualmente. Los metadatos se pueden almacenar en la memoria o guardar en el disco.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ApplyEditAndContinue](imetadataemit-applyeditandcontinue-method.md)|Actualiza el ámbito del ensamblado actual con los cambios realizados en el especificado `pImport` .|  
|[Método DefineCustomAttribute](imetadataemit-definecustomattribute-method.md)|Crea una definición para un atributo personalizado con la firma de metadatos especificada, que se va a adjuntar al objeto especificado y obtiene un token para esa definición de atributo personalizado.|  
|[Método DefineEvent](imetadataemit-defineevent-method.md)|Crea una definición para un evento con la firma de metadatos especificada y obtiene un token para esa definición de evento.|  
|[DefineField (Método)](imetadataemit-definefield-method.md)|Crea una definición para un campo con la firma de metadatos especificada y obtiene un token para esa definición de campo.|  
|[Método DefineImportMember](imetadataemit-defineimportmember-method.md)|Crea una definición para un miembro de un tipo que se define en un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[Método DefineImportType](imetadataemit-defineimporttype-method.md)|Crea una definición para una referencia a un tipo que se define en un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[Método DefineMemberRef](imetadataemit-definememberref-method.md)|Crea una definición para una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[Método DefineMethod](imetadataemit-definemethod-method.md)|Crea una definición para un método con la firma especificada y devuelve un token a esa definición de método.|  
|[Método DefineMethodImpl](imetadataemit-definemethodimpl-method.md)|Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token a esa definición de implementación de método.|  
|[Método DefineModuleRef](imetadataemit-definemoduleref-method.md)|Crea la firma de metadatos para un módulo con el nombre especificado.|  
|[Método DefineNestedType](imetadataemit-definenestedtype-method.md)|Crea la firma de metadatos de una definición de tipo y devuelve un `mdTypeDef` token para ese tipo, especificando además que el tipo definido es un miembro del tipo al que hace referencia `tdEncloser` .|  
|[Método DefineParam](imetadataemit-defineparam-method.md)|Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.|  
|[Método DefinePermissionSet](imetadataemit-definepermissionset-method.md)|Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un token para esa definición de conjunto de permisos.|  
|[Método DefinePinvokeMap](imetadataemit-definepinvokemap-method.md)|Establece las características de la firma PInvoke del método al que hace referencia el token especificado.|  
|[Método DefineProperty](imetadataemit-defineproperty-method.md)|Crea una definición de propiedad para el tipo especificado, con los `get` descriptores de acceso de los métodos y especificados `set` , y obtiene un token para esa definición de propiedad.|  
|[Método DefineSecurityAttributeSet](imetadataemit-definesecurityattributeset-method.md)|Crea un conjunto de permisos de seguridad que se van a adjuntar al objeto al que hace referencia el token especificado.|  
|[Método DefineTypeDef](imetadataemit-definetypedef-method.md)|Crea una definición de tipo para un Common Language Runtime tipo y obtiene un símbolo (token) de metadatos para esa definición de tipo.|  
|[Método DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md)|Obtiene un símbolo (token) de metadatos para un tipo que se define en otro módulo fuera del ámbito actual.|  
|[Método DefineUserString](imetadataemit-defineuserstring-method.md)|Obtiene un símbolo (token) de metadatos para la cadena literal especificada.|  
|[Método DeleteClassLayout](imetadataemit-deleteclasslayout-method.md)|Destruye la firma de metadatos de diseño de clase para el tipo al que hace referencia el token especificado.|  
|[Método DeleteFieldMarshal](imetadataemit-deletefieldmarshal-method.md)|Destruye la firma de metadatos de serialización de PInvoke para el objeto al que hace referencia el token especificado.|  
|[Método DeletePinvokeMap](imetadataemit-deletepinvokemap-method.md)|Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.|  
|[Método DeleteToken](imetadataemit-deletetoken-method.md)|Elimina el token especificado del ámbito de metadatos actual.|  
|[Método GetSaveSize](imetadataemit-getsavesize-method.md)|Obtiene el tamaño binario estimado del ensamblado en el ámbito actual.|  
|[Método GetTokenFromSig](imetadataemit-gettokenfromsig-method.md)|Obtiene un token para la firma de metadatos especificada.|  
|[Método GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md)|Obtiene un símbolo (token) de metadatos para el tipo con la firma de metadatos especificada.|  
|[Método Merge](imetadataemit-merge-method.md)|Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.|  
|[Método MergeEnd](imetadataemit-mergeend-method.md)|Combina en el ámbito actual todos los ámbitos de metadatos especificados por una o varias llamadas anteriores a `IMetaDataEmit::Merge` .|  
|[Save (método)](imetadataemit-save-method.md)|Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.|  
|[Método SaveToMemory](imetadataemit-savetomemory-method.md)|Guarda todos los metadatos del ámbito actual en el área de memoria especificada.|  
|[Método SaveToStream](imetadataemit-savetostream-method.md)|Guarda todos los metadatos del ámbito actual en el especificado `IStream` .|  
|[Método SetClassLayout](imetadataemit-setclasslayout-method.md)|Establece o actualiza la firma de diseño de clase de un tipo definido por una llamada anterior a `IMetaDataEmit::DefineTypeDef` .|  
|[Método SetCustomAttributeValue](imetadataemit-setcustomattributevalue-method.md)|Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a `IMetaDataEmit::DefineCustomAttribute` .|  
|[Método SetEventProps](imetadataemit-seteventprops-method.md)|Establece o actualiza la característica especificada de un evento definido por una llamada anterior a `IMetaDataEmit::DefineEvent` .|  
|[Método SetFieldMarshal](imetadataemit-setfieldmarshal-method.md)|Establece la información de serialización de PInvoke para el campo, el valor devuelto por el método o el parámetro de método al que hace referencia el token especificado.|  
|[Método SetFieldProps](imetadataemit-setfieldprops-method.md)|Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.|  
|[Método SetFieldRVA](imetadataemit-setfieldrva-method.md)|Establece un valor de variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.|  
|[Método SetHandler](imetadataemit-sethandler-method.md)|Establece el método al que hace referencia el `IUnknown` puntero especificado como una devolución de llamada de notificación para las reasignaciones de token.|  
|[Método SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md)|Establece o actualiza la firma de metadatos de la implementación del método heredado a la que hace referencia el token especificado.|  
|[Método SetMethodProps](imetadataemit-setmethodprops-method.md)|Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a `IMetaDataEmit::DefineMethod` .|  
|[Método SetModuleProps](imetadataemit-setmoduleprops-method.md)|Actualiza las referencias a un módulo definido por una llamada anterior a `IMetaDataEmit::DefineModuleRef` .|  
|[Método SetParamProps](imetadataemit-setparamprops-method.md)|Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a `IMetaDataEmit::DefineParam` .|  
|[Método SetParent](imetadataemit-setparent-method.md)|Establece que el miembro especificado, tal y como se define en una llamada anterior a `IMetaDataEmit::DefineMemberRef` , es un miembro del tipo especificado, tal y como se define en una llamada anterior a `IMetaDataEmit::DefineTypeDef` .|  
|[Método SetPermissionSetProps](imetadataemit-setpermissionsetprops-method.md)|Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a `IMetaDataEmit::DefinePermissionSet` .|  
|[Método SetPinvokeMap](imetadataemit-setpinvokemap-method.md)|Establece o cambia las características de la firma PInvoke de un método, tal como se define en una llamada anterior a `IMetaDataEmit::DefinePinvokeMap` .|  
|[Método SetPropertyProps](imetadataemit-setpropertyprops-method.md)|Establece las características almacenadas en los metadatos de una propiedad definida por una llamada anterior a `IMetaDataEmit::DefineProperty` .|  
|[Método SetRVA](imetadataemit-setrva-method.md)|Establece la dirección virtual relativa del método especificado.|  
|[Método SetTypeDefProps](imetadataemit-settypedefprops-method.md)|Establece las características de un tipo definido por una llamada anterior a `IMetaDataEmit::DefineTypeDef` .|  
|[Método TranslateSigWithScope](imetadataemit-translatesigwithscope-method.md)|Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
