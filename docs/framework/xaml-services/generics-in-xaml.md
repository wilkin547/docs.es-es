---
title: "Generics in XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "generics [XAML Services]"
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Generics in XAML
Los servicios XAML de .NET Framework implementados en System.Xaml proporcionan compatibilidad para utilizar tipos genéricos de CLR.  Esta compatibilidad incluye especificar las restricciones de genéricos como un argumento de tipo y exigir la restricción llamando al método `Add` adecuado para los casos de colección genéricos.  En este tema se describen aspectos relativos al uso y las referencias de los tipos genéricos en XAML.  
  
## x:TypeArguments  
 `x:TypeArguments` es una directiva definida por el lenguaje XAML.  Cuando se utiliza como un miembro de un tipo XAML respaldado por un tipo genérico, `x:TypeArguments` pasa los argumentos de tipo restrictivos del constructor genérico al de respaldo.  Para obtener la sintaxis de referencia que pertenece al uso de los servicios XAML de .NET Framework de `x:TypeArguments`, que incluye ejemplos de sintaxis, vea [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Dado que `x:TypeArguments` toma una cadena y tiene respaldo de convertidor de tipos, normalmente se declara en el uso de XAML como un atributo.  
  
 En el flujo de nodo XAML, la información declarada por `x:TypeArguments` se puede obtener de <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> en una posición `StartObject` en el flujo de nodo.  El valor devuelto de <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> es una lista de valores de <xref:System.Xaml.XamlType>.  Para determinar si un tipo XAML representa un tipo genérico, se puede llamar a <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=fullName>.  
  
## Reglas y convenciones de sintaxis para genéricos en XAML  
 En XAML, un tipo genérico se debe representar siempre como un genérico restringido; un genérico sin restricciones nunca está presente en el sistema de tipos de XAML ni en un flujo de nodo XAML, y no se puede representar en el marcado XAML.  Se puede hacer referencia a un genérico dentro de la sintaxis de atributo de XAML, para los casos donde es una restricción de tipo anidado de un genérico al que se hace referencia mediante `x:TypeArguments`, o para los casos donde `x:Type` proporciona una referencia de tipo CLR para un tipo genérico.  Esto se admite a través de la clase <xref:System.Xaml.Schema.XamlTypeTypeConverter> definida por los servicios XAML de .NET Framework.  
  
 La forma de sintaxis de atributo de XAML habilitada por <xref:System.Xaml.Schema.XamlTypeTypeConverter> modifica la convención de la sintaxis de MSIL\/CLR típica que utiliza corchetes angulares para los tipos y restricciones de los genéricos, y en su lugar sustituye los paréntesis para el contenedor de restricción.  Para obtener un ejemplo, vea [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## Genéricos y características de XAML 2009  
 Si utiliza XAML 2009 en lugar de asignar los tipos base de CLR para obtener tipos XAML para los primitivos del lenguaje comunes, puede utilizar los [tipos integrados de XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) como elementos de información en `x:TypeArguments`.  Por ejemplo, podría declarar lo siguiente \(las asignaciones de prefijo no se muestran, pero `x` es el espacio de nombres XAML del lenguaje XAML para XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## Compatibilidad con los genéricos en WPF y otros marcos v3.5  
 Para el uso de XAML 2006 destinado específicamente a WPF, [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar en el mismo elemento que `x:TypeArguments` y ese elemento debe ser el elemento raíz en un documento XAML.  El elemento raíz debe asignarse a un tipo genérico con, al menos, un argumento de tipo.  Un ejemplo de ello sería <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Las posibles soluciones alternativas para admitir los usos genéricos incluyen definir una extensión de marcado personalizada que puede devolver tipos genéricos, o proporcionar una definición de clase contenedora que deriva de un tipo genérico, pero quita la información de estructura jerárquica de la restricción genérica en su propia definición de clase.  
  
 En WPF y la versión de destino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], puede utilizar las características de XAML 2009 junto con `x:TypeArguments`, pero solo para XAML dinámico \(XAML no compilado por marcado\).  El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten actualmente las palabras clave y características de XAML 2009.  
  
 Los flujos de trabajo personalizados de [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] para [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] no admiten el uso de XAML genérico.  
  
## Vea también  
 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)   
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)