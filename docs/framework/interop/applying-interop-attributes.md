---
title: "Applying Interop Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "design-time attributes"
  - ".NET Framework, exposing components to COM"
  - "attributes [.NET Framework], design-time functionality"
  - "conversion-tool attributes"
  - "attributes [.NET Framework], interop-specific"
  - "attributes [.NET Framework], conversion-tool"
  - "interoperation with unmanaged code, applying attributes"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
  - "COM interop, applying attributes"
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Applying Interop Attributes
El espacio de nombres <xref:System.Runtime.InteropServices> proporciona tres categorías de atributos específicos de la interoperabilidad: los que el usuario aplica en tiempo de diseño, los que las API y las herramientas de interoperabilidad COM aplican durante el proceso de conversión y los que aplica el usuario o la interoperabilidad COM.  
  
 Si no está familiarizado con la tarea de aplicar atributos al código administrado, vea [Extender metadatos mediante atributos](../../../docs/standard/attributes/index.md).  Del mismo modo que se aplican otros atributos personalizados, los atributos específicos de la interoperabilidad pueden aplicarse a tipos, métodos, propiedades, parámetros, campos y otros miembros.  
  
## Atributos en tiempo de diseño  
 Se puede ajustar el resultado del proceso de conversión realizado por las API y las herramientas de interoperabilidad COM utilizando atributos en tiempo de diseño.  En la siguiente tabla se describen los atributos que se pueden aplicar al código fuente administrado.  En alguna ocasión, las herramientas de interoperabilidad COM podrían aplicar también los atributos descritos en esta tabla.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Especifica si las referencias del tipo deben calcularse utilizando Automation Marshaler o un proxy y un código auxiliar personalizados.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Controla el tipo de interfaz generada para una clase.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Identifica el CLSID de la coclase original importada de una biblioteca de tipos.<br /><br /> Las herramientas de interoperabilidad COM aplican normalmente este atributo.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Indica que una definición de interfaz o coclase se importó desde una biblioteca de tipos COM.  El motor en tiempo de ejecución utiliza esta marca para conocer la forma de activar el tipo y de calcular sus referencias.  Este atributo impide que el tipo vuelva a exportarse a la biblioteca de tipos.<br /><br /> Las herramientas de interoperabilidad COM aplican normalmente este atributo.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Indica que debe llamarse a un método cuando el ensamblado se registra para su uso desde COM, de modo que el código escrito por el usuario pueda ejecutarse durante el proceso de registro.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Identifica las interfaces que son orígenes de eventos para la clase.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Indica que debe llamarse a un método cuando se anula el registro del ensamblado desde COM, de modo que el código escrito por el usuario pueda ejecutarse durante el proceso.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Hace que los tipos no sean visibles para COM cuando el valor del atributo es **false**.  Este atributo puede aplicarse a un tipo individual o a todo un ensamblado para controlar la visibilidad de COM.  De forma predeterminada, todos los tipos públicos administrados son visibles; este atributo no es necesario para hacerlos visibles.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Especifica el identificador de envío \(DISPID\) COM de un método o campo.  Este atributo contiene el identificador de envío del método, campo o propiedad que describe.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Indica la posición física de cada campo dentro de una clase cuando se utiliza con **StructLayoutAttribute** y **LayoutKind** está establecido en Explicit.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Especifica el identificador único global \(GUID\) de una clase, de una interfaz o de toda una biblioteca de tipos.  La cadena que se pasa al atributo debe tener el formato de un argumento de constructor aceptable para el tipo **System.Guid**.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|[IDispatchImpAttribute](frlrfsystemruntimeinteropservicesidispatchimplattributeclasstopic)|Indica la implementación de la interfaz **IDispatch** que Common Language Runtime utiliza cuando expone interfaces duales e interfaces Dispinterface en COM.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Indica que el cálculo de referencias de los datos debe realizarse en el llamador.  Puede utilizarse en parámetros de atributo.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Controla la forma en que una interfaz administrada se expone en los clientes COM \(dual, derivada de Iunknown o sólo IDispatch\).<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Indica que un prototipo de método no administrado espera un parámetro LCID.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Indica la forma en que deben calcularse las referencias a los datos de campos o parámetros entre el código administrado y el código no administrado.  Este atributo es siempre opcional ya que cada tipo de datos tiene un comportamiento predeterminado para el cálculo de referencias.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Indica que un parámetro es opcional.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Indica que las referencias de los datos de un campo o parámetro deben calcularse desde el objeto destinatario de la llamada al llamador.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Suprime la transformación del prototipo de retval o HRESULT que tiene lugar normalmente durante las llamadas de interoperabilidad.  El atributo afecta al cálculo de referencias y a la exportación de bibliotecas de tipos.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Especifica el identificador de programa \(ProgID\) de una clase de .NET Framework.  Puede utilizarse en las clases de atributos.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Controla la distribución física de los campos de una clase.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
  
## Atributos de la herramienta de conversión  
 En la siguiente tabla se describen los atributos que las herramientas de interoperabilidad COM aplican durante el proceso de conversión.  Estos atributos no se aplican en tiempo de diseño.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Indica el alias COM del tipo de parámetro o campo.  Este atributo puede aplicarse a parámetros, campos o valores devueltos.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Indica que se perdió información acerca de una clase o interfaz al importarse desde una biblioteca de tipos a un ensamblado.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Identifica la interfaz de origen y la clase que implementa los métodos de la interfaz de eventos.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Indica que el ensamblado se importó originalmente desde una biblioteca de tipos COM.  Este atributo contiene la definición de biblioteca de tipos de la biblioteca de tipos original.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Contiene **FUNCFLAGS** que se importaron originalmente para esta función desde la biblioteca de tipos COM.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Contiene **TYPEFLAGS** que se importaron originalmente para este tipo desde la biblioteca de tipos COM.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Contiene **VARFLAGS** que se importaron originalmente para esta variable desde la biblioteca de tipos COM.|  
  
## Vea también  
 <xref:System.Runtime.InteropServices>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Atributos](../../../docs/standard/attributes/index.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)