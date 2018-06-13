---
title: Enumeraciones para metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- enumerations [.NET Framework metadata]
- metadata enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], metadata
ms.assetid: 711ab251-cfdb-4280-aaa6-9bc1b341cdc3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f92b87cc2748a709361ff2c0c8129db5f7fe6046
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460973"
---
# <a name="metadata-enumerations"></a>Enumeraciones para metadatos
En esta sección se describen las enumeraciones no administradas que la API de metadatos usa.  
  
## <a name="in-this-section"></a>En esta sección  
 [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)  
 Contiene valores que describen las características en tiempo de ejecución de un ensamblado.  
  
 [AssemblyRefFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)  
 Contiene valores que describen las características de una referencia de ensamblado.  
  
 [CeeSectionAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/ceesectionattr-enumeration.md)  
 Proporciona valores que especifican los atributos de una sección para su uso por el [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaz.  
  
 [CeeSectionRelocType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)  
 Proporciona valores para influir en el tipo de `reloc` instrucción se emite en una llamada a la [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md) método.  
  
 [COINITICOR (enumeración)](../../../../docs/framework/unmanaged-api/metadata/coiniticor-enumeration.md)  
 Especifica las constantes utilizadas por [CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md) al inicializar common language runtime.  
  
 [COINITIEE (enumeración)](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)  
 Especifica las constantes utilizadas por [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) al inicializar common language runtime.  
  
 [CorArgType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corargtype-enumeration.md)  
 Contiene valores que describen el tipo nativo de un identificador en tiempo de ejecución.  
  
 [CorAssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)  
 Contiene valores que describen los metadatos aplicados a una compilación de ensamblado.  
  
 [CorAttributeTargets (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corattributetargets-enumeration.md)  
 Especifica los elementos de aplicación en los que se permite aplicar un atributo.  
  
 [CorCallingConvention (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corcallingconvention-enumeration.md)  
 Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.  
  
 [CorCheckDuplicatesFor (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md)  
 Contiene los valores usados durante las comprobaciones de duplicados.  
  
 [CorDeclSecurity (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)  
 Contiene valores que describen los tipos de seguridad declarativa usados por el CLR.  
  
 CorElementType  
 Contiene valores que describen el tipo nativo subyacente de un CLR <xref:System.Type>.  
  
 [CorErrorIfEmitOutOfOrder (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md)  
 Contiene valores de marca que indican las condiciones en las que se debe generar un mensaje de error cuando los metadatos se emiten sin orden.  
  
 [CorEventAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/coreventattr-enumeration.md)  
 Contiene valores que describen los metadatos de un evento.  
  
 [CorFieldAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfieldattr-enumeration.md)  
 Contiene valores que describen los metadatos de un campo.  
  
 [CorFileFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)  
 Contiene valores que describen el tipo de archivo definido en una llamada a la [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) método.  
  
 [CorFileMapping (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)  
 Contiene valores que describen el tipo de asignación de archivo que se devuelve de una llamada a la [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) método.  
  
 [CorGenericParamAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)  
 Contiene valores que describen la <xref:System.Type> parámetros de tipos genéricos, como usan en las llamadas a la [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md) método.  
  
 [CorImportOptions (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)  
 Contiene valores de marca que controlan el comportamiento durante la importación de un ensamblado fuera del ámbito actual.  
  
 [CorLinkerOptions (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md)  
 Especifica marcas para seleccionar las opciones del vinculador de metadatos.  
  
 [CorLocalRefPreservation (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)  
 Contiene valores de marca para el tratamiento de referencias locales.  
  
 [CorManifestResourceFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)  
 Contiene valores que describen la visibilidad de los recursos codificados en un manifiesto de ensamblado.  
  
 [CorMethodAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)  
 Contiene valores que describen los metadatos de un método.  
  
 [CorMethodImpl (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)  
 Contiene valores que describen las características de implementación de un método.  
  
 [CorMethodSemanticsAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md)  
 Contiene valores que describen la relación entre un método y una propiedad o evento asociados.  
  
 [CorNativeLinkFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)  
 Proporciona valores de marca que el vinculador usa al vincular código nativo.  
  
 [CorNativeLinkType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 Proporciona valores que indican el tipo vinculado en código nativo.  
  
 [CorNativeType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornativetype-enumeration.md)  
 Contiene valores que describen los tipos nativos no administrados.  
  
 [CorNotificationForTokenMovement (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md)  
 Contiene valores de marca que influyen en las notificaciones durante el movimiento de tokens.  
  
 [CorOpenFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)  
 Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.  
  
 [CorParamAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corparamattr-enumeration.md)  
 Contiene valores que describen los metadatos de un parámetro de método.  
  
 [CorPEKind (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)  
 Contiene valores que describen un archivo portable ejecutable, tal como lo devuelve una llamada a la [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md) método.  
  
 [CorPinvokeMap (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)  
 Contiene valores que describen las características de una llamada PInvoke.  
  
 [CorPropertyAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)  
 Contiene valores que describen los metadatos de una propiedad.  
  
 [CorRefToDefCheck (enumeración)](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)  
 Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.  
  
 [CorRegFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corregflags-enumeration.md)  
 Proporciona valores de marca usados para el registro al instalar un módulo o compuesto.  
  
 [CorSaveSize (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)  
 Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.  
  
 [CorSerializationType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corserializationtype-enumeration.md)  
 Contiene valores que describen la manera en que el CLR serializa un objeto. Por lo general, estos valores corresponden a valores CorElementType.  
  
 [CorSetENC (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md)  
 Contiene valores que se usan para influir en el comportamiento durante la generación de metadatos.  
  
 [CorThreadSafetyOptions (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md)  
 Especifica marcas para seleccionar opciones de seguridad para subprocesos.  
  
 [CorTokenType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cortokentype-enumeration.md)  
 Contiene valores que indican el tipo de objeto al que un token de metadatos hace referencia.  
  
 [CorTypeAttr (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)  
 Contiene valores que indican los metadatos de tipo.  
  
 [CorUnmanagedCallingConvention (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corunmanagedcallingconvention-enumeration.md)  
 Contiene valores que describen las convenciones de llamada no administradas.  
  
 [CorValidatorModuleType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md)  
 Proporciona los valores utilizados por la [IMetaDataValidate](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md) interfaz para especificar el tipo del módulo (archivo PE frente a archivo .obj).  
  
 [COUNINITIEE (enumeración)](../../../../docs/framework/unmanaged-api/metadata/couninitiee-enumeration.md)  
 Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
  
 [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [Uniones de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
