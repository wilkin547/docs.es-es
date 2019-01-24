---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f28facc8acb430de4aa255208a62c5fc61f12cd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727669"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit (Interfaz)
Proporciona métodos para crear, modificar y guardar los metadatos sobre el ensamblado en el ámbito definido actualmente. Los metadatos se pueden almacenar en memoria o guardado en el disco.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ApplyEditAndContinue (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|El ámbito de ensamblado actual se actualiza con los cambios realizados en la instancia especificada `pImport`.|  
|[DefineCustomAttribute (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Crea una definición para un atributo personalizado con la firma de metadatos especificado, que se adjuntará al objeto especificado y obtiene un token para esa definición de atributo personalizado.|  
|[DefineEvent (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Crea una definición para un evento con la firma de metadatos especificados y obtiene un token para esa definición de evento.|  
|[DefineField (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Crea una definición para un campo con la firma de metadatos especificados y obtiene un token para esa definición de campo.|  
|[DefineImportMember (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Crea una definición para un miembro de un tipo que se define en un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[DefineImportType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Crea una definición para una referencia a un tipo que se define en un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[DefineMemberRef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Crea una definición para una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.|  
|[DefineMethod (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Crea una definición para un método con la firma especificada y devuelve un token para esa definición de método.|  
|[DefineMethodImpl (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token para esa definición de implementación del método.|  
|[DefineModuleRef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Crea la firma de metadatos para un módulo con el nombre especificado.|  
|[DefineNestedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Crea la firma de metadatos de una definición de tipo y devuelve un `mdTypeDef` token para ese tipo, y además especifica que el tipo definido es un miembro del tipo al que hace referencia `tdEncloser`.|  
|[DefineParam (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.|  
|[DefinePermissionSet (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Crea una definición para un conjunto de permisos con la firma de metadatos especificado y obtiene un token para esa definición del conjunto de permisos.|  
|[DefinePinvokeMap (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Establece las características de la firma PInvoke del método al que hace referencia el token especificado.|  
|[DefineProperty (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Crea una definición de propiedad para el tipo especificado, con la especificación `get` y `set` los descriptores de acceso de método y obtiene un token para esa definición de propiedad.|  
|[DefineSecurityAttributeSet (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Crea un conjunto de permisos de seguridad que se va a adjuntar al objeto al que hace referencia el token especificado.|  
|[DefineTypeDef (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Crea una definición de tipo para un tipo de common language runtime y obtiene un token de metadatos a la definición de ese tipo.|  
|[DefineTypeRefByName (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Obtiene los metadatos de un token para un tipo que se define en otro módulo fuera del ámbito actual.|  
|[DefineUserString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Obtiene los metadatos de un token para la cadena literal especificada.|  
|[DeleteClassLayout (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Destruye la firma de metadatos de diseño de clase para el tipo al que hace referencia el token especificado.|  
|[DeleteFieldMarshal (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Destruye la firma de metadatos para el objeto al que hace referencia el token especificado de cálculo de referencias de PInvoke.|  
|[DeletePinvokeMap (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.|  
|[DeleteToken (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Elimina el token especificado de ámbito de metadatos actual.|  
|[GetSaveSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Obtiene el tamaño estimado de binario del ensamblado en el ámbito actual.|  
|[GetTokenFromSig (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Obtiene un token para la firma de metadatos especificado.|  
|[GetTokenFromTypeSpec (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Obtiene los metadatos de un token para el tipo con la firma de metadatos especificado.|  
|[Merge (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Agrega el ámbito importado especificado a la lista de ámbitos que se combinarán.|  
|[MergeEnd (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Combina en el actual ámbito de todos los ámbitos de los metadatos especificados por una o varias llamadas anteriores al `IMetaDataEmit::Merge`.|  
|[Save (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.|  
|[SaveToMemory (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Guarda todos los metadatos en el ámbito actual en el área de memoria especificada.|  
|[SaveToStream (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Guarda todos los metadatos en el ámbito actual a los especificados `IStream`.|  
|[SetClassLayout (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Establece o actualiza la firma de diseño de clase de un tipo definido por una llamada anterior a `IMetaDataEmit::DefineTypeDef`.|  
|[SetCustomAttributeValue (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a `IMetaDataEmit::DefineCustomAttribute`.|  
|[SetEventProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Establece o actualiza la característica especificada de un evento definido por una llamada anterior a `IMetaDataEmit::DefineEvent`.|  
|[SetFieldMarshal (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Establece la información para el parámetro de campo, el valor devuelto del método o el método al que hace referencia el token especificado de cálculo de referencias de PInvoke.|  
|[SetFieldProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.|  
|[SetFieldRVA (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Establece un valor de la variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.|  
|[SetHandler (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Establece el método al que hace referencia especificado `IUnknown` puntero como una devolución de llamada de notificación para las reasignaciones de token.|  
|[SetMethodImplFlags (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Establece o actualiza la firma de metadatos de la implementación del método heredado que hace referencia el token especificado.|  
|[SetMethodProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a `IMetaDataEmit::DefineMethod`.|  
|[SetModuleProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Actualiza las referencias a un módulo definido por una llamada anterior a `IMetaDataEmit::DefineModuleRef`.|  
|[SetParamProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Establece o cambia las características de un parámetro de método que se ha definido por una llamada anterior a `IMetaDataEmit::DefineParam`.|  
|[SetParent (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Establece que el miembro especificado, tal como se define mediante una llamada anterior a `IMetaDataEmit::DefineMemberRef`, es un miembro del tipo especificado, tal como se define mediante una llamada anterior a `IMetaDataEmit::DefineTypeDef`.|  
|[SetPermissionSetProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a `IMetaDataEmit::DefinePermissionSet`.|  
|[SetPinvokeMap (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Establece o cambia las características de una firma de método PInvoke, tal como se define mediante una llamada anterior a `IMetaDataEmit::DefinePinvokeMap`.|  
|[SetPropertyProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Establece las características que se almacenan en los metadatos para una propiedad definida por una llamada anterior a `IMetaDataEmit::DefineProperty`.|  
|[SetRVA (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Establece la dirección virtual relativa del método especificado.|  
|[SetTypeDefProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Establece las características de un tipo definido por una llamada anterior a `IMetaDataEmit::DefineTypeDef`.|  
|[TranslateSigWithScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
