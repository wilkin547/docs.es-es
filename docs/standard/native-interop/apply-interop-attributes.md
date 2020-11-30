---
title: Aplicar atributos de interoperabilidad
description: En este artículo se resumen los atributos de interoperabilidad COM del espacio de nombres System.Runtime.InteropServices, incluidos los atributos de tiempo de diseño y herramienta de conversión.
ms.date: 03/30/2017
helpviewer_keywords:
- design-time attributes
- .NET, exposing components to COM
- attributes [.NET], design-time functionality
- conversion-tool attributes
- attributes [.NET], interop-specific
- attributes [.NET], conversion-tool
- interoperation with unmanaged code, applying attributes
- interoperation with unmanaged code, exposing .NET components
- COM interop, exposing COM components
- COM interop, applying attributes
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
ms.openlocfilehash: 38632c5a1f462c3a7b537978fde81424916746da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706299"
---
# <a name="applying-interop-attributes"></a>Aplicar atributos de interoperabilidad

El espacio de nombres <xref:System.Runtime.InteropServices> proporciona tres categorías de atributos específicos de interoperabilidad: los que se aplican por parte del usuario en tiempo de diseño, los que se aplican mediante herramientas de interoperabilidad COM y durante el proceso de conversión, y los que se aplican por parte del usuario o interoperabilidad COM.  
  
 Si no está familiarizado con la tarea de aplicar atributos al código administrado, vea [Extender metadatos mediante atributos](../attributes/index.md). Al igual que otros atributos personalizados, puede aplicar atributos específicos de interoperabilidad a tipos, métodos, propiedades, parámetros, campos y otros miembros.  
  
## <a name="design-time-attributes"></a>Atributos en tiempo de diseño  

 Puede ajustar el resultado del proceso de conversión realizado por las API y las herramientas de interoperabilidad COM mediante atributos en tiempo de diseño. En la tabla siguiente se describen los atributos que se pueden aplicar al código fuente administrado. En ocasiones, es posible que las herramientas de interoperabilidad COM también apliquen los atributos descritos en esta tabla.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Especifica si el tipo debe serializarse mediante el contador de referencias de Automation o un proxy personalizado y código auxiliar.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Controla el tipo de interfaz generada para una clase.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Identifica el CLSID de la coclase original importada desde una biblioteca de tipos.<br /><br /> Las herramientas de interoperabilidad COM aplican normalmente este atributo.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Indica que una definición de interfaz o coclase se importó desde una biblioteca de tipos COM. El tiempo de ejecución usa este indicador para saber cómo activar y serializar el tipo. Este atributo prohíbe que el tipo se vuelva a exportar a una biblioteca de tipos.<br /><br /> Las herramientas de interoperabilidad COM aplican normalmente este atributo.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Indica que debe llamarse a un método cuando el ensamblado se registra para su uso desde COM, por lo que se puede ejecutar código escrito por el usuario durante el proceso de registro.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Identifica las interfaces que son orígenes de eventos para la clase.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Indica que debe llamarse a un método cuando se anula el registro del ensamblado desde COM, para que se pueda ejecutar código escrito por el usuario durante el proceso.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Representa tipos visibles para COM cuando el valor del atributo es igual a **false**. Este atributo se puede aplicar a un tipo individual o a un ensamblado completo para controlar la visibilidad de COM. De forma predeterminada, todos los tipos públicos son visibles; no se necesita el atributo para hacerlos visibles.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Especifica el identificador de envío (DISPID) de COM de un método o campo. Este atributo contiene el DISPID para el método, campo o propiedad que describe.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute>|Indica la interfaz predeterminada para una clase COM implementada en .NET.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Indica la posición física de cada campo dentro de una clase cuando se usa con **StructLayoutAttribute**, y **LayoutKind** se establece en Explicit.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Especifica el identificador único global (GUID) de una clase, interfaz o una biblioteca de tipos completa. La cadena que se pasa al atributo debe tener un formato que sea un argumento de constructor aceptable para el tipo de **System.Guid**.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute>|Indica la implementación de la interfaz **IDispatch** que usa el Common Language Runtime cuando expone interfaces duales e interfaces dispinterface a COM.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Indica que los datos se deben serializar en el llamador. Se puede usar para parámetros de atributo.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Controla la forma en que se expone una interfaz administrada a los clientes COM (Dual, derivada de IUnknown o solo IDispatch).<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Indica que una firma de método no administrado espera un parámetro LCID.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Indica cómo se deben serializar los datos de campos o parámetros entre código administrado y no administrado. El atributo siempre es opcional porque cada tipo de datos tiene el comportamiento de serialización predeterminado.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Indica que un parámetro es opcional.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Indica que los datos de un campo o parámetro deben serializarse desde un objeto que se llama a su llamador.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Suprime la transformación de la firma retval o del valor HRESULT que normalmente tiene lugar durante las llamadas de interoperabilidad. El atributo afecta a la serialización, así como a la exportación de bibliotecas de tipos.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Especifica el valor ProgID de una clase de .NET. Se puede usar para clases de atributos.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Controla el diseño físico de los campos de una clase.<br /><br /> Las herramientas de interoperabilidad COM pueden aplicar este atributo.|  
  
## <a name="conversion-tool-attributes"></a>Atributos de la herramienta de conversión  

 En la tabla siguiente se describen los atributos que las herramientas de interoperabilidad COM aplican durante el proceso de conversión. Estos atributos no se aplican en tiempo de diseño.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Indica el alias COM de un parámetro o tipo de campo. Puede usarse para parámetros de atributo, campos o valores devueltos.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Indica que se perdió la información sobre una clase o interfaz cuando se importó desde una biblioteca de tipos a un ensamblado.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Identifica la interfaz de origen y la clase que implementa los métodos de la interfaz de eventos.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Indica que el ensamblado se importó originalmente desde una biblioteca de tipos COM. Este atributo contiene la definición de biblioteca de tipos de la biblioteca de tipos original.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Contiene los **FUNCFLAGS** que se importaron originalmente para esta función desde la biblioteca de tipos COM.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Contiene los **TYPEFLAGS** que se importaron originalmente para este tipo desde la biblioteca de tipos COM.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Contiene los **VARFLAGS** que se importaron originalmente para esta variable desde la biblioteca de tipos COM.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices>
- [Exponer componentes de .NET Framework en COM](../../framework/interop/exposing-dotnet-components-to-com.md)
- [Atributos](../attributes/index.md)
- [Habilitar tipos de .NET para la interoperación](qualify-net-types-for-interoperation.md)
- [Empaquetar un ensamblado de .NET Framework para COM](../../framework/interop/packaging-an-assembly-for-com.md)
