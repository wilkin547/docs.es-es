---
title: IMetaDataImport (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport
helpviewer_keywords:
- IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a65eae91bf3b44fc2b49588ead5ed178d7326f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180406"
---
# <a name="imetadataimport-interface"></a>IMetaDataImport (Interfaz)
Proporciona métodos para importar y manipular los metadatos existentes desde un archivo portable ejecutable (PE) u otro origen, como una biblioteca de tipos o un archivo binario de metadatos independiente en tiempo de ejecución.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (Método)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-closeenum-method.md)|Cierra el enumerador con el identificador especificado.|  
|[Método CountEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-countenum-method.md)|Obtiene el número de elementos del enumerador con el identificador especificado.|  
|[EnumCustomAttributes (Método)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)|Enumera una lista de tokens de definición de atributos personalizados asociados al tipo o al miembro especificado.|  
|[Método EnumEvents](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumevents-method.md)|Enumera los tokens de definición de eventos del token de TypeDef especificado.|  
|[Método EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)|Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.|  
|[Método EnumFieldsWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfieldswithname-method.md)|Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.|  
|[Método EnumInterfaceImpls](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enuminterfaceimpls-method.md)|Enumera los tokens de MethodDef que representan implementaciones de la interfaz.|  
|[Método EnumMemberRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberrefs-method.md)|Enumera los tokens de MemberRef que representan a miembros del tipo especificado.|  
|[Método EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)|Enumera los tokens de MemberDef que representan a miembros del tipo especificado.|  
|[Método EnumMembersWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberswithname-method.md)|Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.|  
|[Método EnumMethodImpls](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodimpls-method.md)|Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.|  
|[Método EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)|Enumera los tokens de MethodDef que representan métodos del tipo especificado.|  
|[Método EnumMethodSemantics](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodsemantics-method.md)|Enumera las propiedades y los eventos de cambio de propiedad con los que está relacionado el método especificado.|  
|[Método EnumMethodsWithName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodswithname-method.md)|Enumera los métodos que tienen el nombre especificado y que están definidos por el tipo al que hace referencia el token de TypeDef especificado.|  
|[Método EnumModuleRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummodulerefs-method.md)|Enumera los tokens de ModuleRef que representan los módulos importados.|  
|[Método EnumParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumparams-method.md)|Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.|  
|[Método EnumPermissionSets](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumpermissionsets-method.md)|Enumera los permisos de los objetos en un ámbito de metadatos especificado.|  
|[Método EnumProperties](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumproperties-method.md)|Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.|  
|[Método EnumSignatures](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumsignatures-method.md)|Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.|  
|[Método EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)|Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.|  
|[Método EnumTypeRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtyperefs-method.md)|Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.|  
|[Método EnumTypeSpecs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypespecs-method.md)|Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.|  
|[Método EnumUnresolvedMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumunresolvedmethods-method.md)|Enumera los tokens de MemberDef que representan los métodos no resueltos en el ámbito de metadatos actual.|  
|[Método EnumUserStrings](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumuserstrings-method.md)|Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.|  
|[Método FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)|Obtiene el token de FieldDef del campo que es un miembro del tipo especificado y tiene el nombre y la firma de metadatos especificados.|  
|[Método FindMember](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmember-method.md)|Obtiene un puntero al token MemberDef para el miembro definido por el tipo especificado con el nombre y la firma de metadatos especificados.|  
|[Método FindMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmemberref-method.md)|Obtiene un puntero al token MemberRef para el miembro definido por el tipo especificado con el nombre y la firma de metadatos especificados.|  
|[Método FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)|Obtiene un puntero al token MethodDef para el método definido por el tipo especificado con el nombre y la firma de metadatos especificados.|  
|[Método FindTypeDefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtypedefbyname-method.md)|Obtiene un puntero al token de metadatos de TypeDef para el tipo con el nombre especificado.|  
|[Método FindTypeRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtyperef-method.md)|Obtiene un puntero al token de metadatos de TypeRef que hace referencia al tipo en el ámbito de búsqueda especificado con el nombre especificado.|  
|[Método GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)|Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.|  
|[Método GetCustomAttributeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributebyname-method.md)|Obtiene el valor del atributo personalizado a partir de su nombre.|  
|[Método GetCustomAttributeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributeprops-method.md)|Obtiene el valor del atributo personalizado a partir de su token de metadatos.|  
|[Método GetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-geteventprops-method.md)|Obtiene la información de los metadatos (incluidos el tipo declarativo, los métodos de adición y eliminación de delegados y todas las marcas y los demás datos asociados) del evento representado por el token de evento especificado.|  
|[Método GetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldmarshal-method.md)|Obtiene un puntero al tipo nativo y no administrado del campo representado por el token de metadatos del campo especificado.|  
|[Método GetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldprops-method.md)|Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.|  
|[Método GetInterfaceImplProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getinterfaceimplprops-method.md)|Obtiene un puntero a los tokens de metadatos para el tipo que implementa el método especificado y para la interfaz que declara ese método.|  
|[Método GetMemberProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberprops-method.md)|Obtiene información de metadatos (incluidos el nombre, la firma binaria y la dirección virtual relativa) del miembro de tipo al que hace referencia el token de metadatos especificado.|  
|[Método GetMemberRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberrefprops-method.md)|Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.|  
|[Método GetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodprops-method.md)|Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.|  
|[Método GetMethodSemantics](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodsemantics-method.md)|Obtiene un puntero a la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento al que hace referencia el token de EventProp especificado.|  
|[Método GetModuleFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulefromscope-method.md)|Obtiene un puntero al token de metadatos del módulo al que se hace referencia en el ámbito de metadatos actual.|  
|[Método GetModuleRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulerefprops-method.md)|Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.|  
|[Método GetNameFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnamefromtoken-method.md)|Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado.|  
|[Método GetNativeCallConvFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnativecallconvfromsig-method.md)|Obtiene la convención de llamada nativa del método representado por el puntero de firma especificado.|  
|[Método GetNestedClassProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnestedclassprops-method.md)|Obtiene el token de TypeDef del tipo primario envolvente del tipo anidado especificado.|  
|[Método GetParamForMethodIndex](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamformethodindex-method.md)|Obtiene un puntero al token que representa el parámetro en la posición ordinal especificada en la secuencia de parámetros de método para el método representado por el token de MethodDef especificado.|  
|[Método GetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamprops-method.md)|Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.|  
|[Método GetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpermissionsetprops-method.md)|Obtiene los metadatos asociados a System.Security.PermissionSet representados por el token de permiso especificado.|  
|[GetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpinvokemap-method.md)|Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.|  
|[Método GetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpropertyprops-method.md)|Obtiene los metadatos asociados a la propiedad representada por el token especificado.|  
|[Método GetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getrva-method.md)|Obtiene el desplazamiento de la dirección virtual relativa del objeto de código representado por el token especificado.|  
|[Método GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md)|Obtiene el nombre y, si quiere, el identificador de versión del ensamblado o el módulo en el ámbito de metadatos actual.|  
|[Método GetSigFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getsigfromtoken-method.md)|Obtiene la firma de metadatos binaria asociada al token especificado.|  
|[Método GetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypedefprops-method.md)|Devuelve información de metadatos del tipo representado por el token de TypeDef especificado.|  
|[Método GetTypeRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettyperefprops-method.md)|Devuelve los metadatos asociados al tipo al que hace referencia el token de TypeRef especificado.|  
|[Método GetTypeSpecFromToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypespecfromtoken-method.md)|Obtiene la firma de metadatos binaria de la especificación de tipo representada por el token especificado.|  
|[Método GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getuserstring-method.md)|Obtiene la cadena literal representada por el token de metadatos especificado.|  
|[Método IsGlobal](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isglobal-method.md)|Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.|  
|[Método IsValidToken](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isvalidtoken-method.md)|Obtiene un valor que indica si el token especificado contiene una referencia válida a un objeto de código.|  
|[Método ResetEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resetenum-method.md)|Restablece el enumerador especificado a la posición especificada.|  
|[Método ResolveTypeRef](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resolvetyperef-method.md)|Obtiene la información de tipo correspondiente al tipo al que hace referencia el token TypeRef especificado.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `IMetaDataImport` está diseñada, principalmente, para que la utilicen las herramientas y los servicios que importarán la información de tipo (por ejemplo, las herramientas de desarrollo) o que administrarán los componentes implementados (por ejemplo, los servicios de resolución o activación). Los métodos de `IMetaDataImport` se dividen en las siguientes categorías de tareas:  
  
-   Enumerar colecciones de elementos en el ámbito de metadatos.  
  
-   Buscar un elemento que tiene un conjunto específico de características.  
  
-   Obtener las propiedades de un elemento especificado.  
  
-   Los métodos Get están diseñados específicamente para devolver propiedades de un solo valor de un elemento de metadatos. Cuando la propiedad es una referencia a otro elemento, se devuelve un token de ese elemento. Cualquier tipo de entrada de puntero puede ser NULL para indicar que no se solicita el valor concreto. Para obtener las propiedades que son esencialmente objetos de colección (por ejemplo, la colección de interfaces que implementa una clase), utilice los métodos de enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
