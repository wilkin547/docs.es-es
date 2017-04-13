---
title: "x:Type Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:TypeExtension"
  - "Type"
  - "x:Type"
  - "xType"
  - "TypeExtension"
helpviewer_keywords: 
  - "x:Type markup extension [XAML Services]"
  - "XAML [XAML Services], x:Type markup extension"
  - "XAML [XAML Services], TargetType attribute"
  - "TargetType attribute [XAML Services]"
  - "Type markup extension in XAML [XAML Services]"
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Type Markup Extension
Proporciona el objeto de CLR <xref:System.Type> que es el tipo subyacente para un tipo XAML especificado.  
  
## Uso de atributos XAML  
  
```  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## Uso de elementos de objeto XAML  
  
```  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`prefix`|Opcional.  Prefijo que asigna un espacio de nombres XAML no predeterminado.  No suele ser necesario especificar un prefijo.  Vea la sección Comentarios.|  
|`typeNameValue`|Obligatorio.  Nombre de tipo que se puede resolver para hallar el espacio de nombres XAML predeterminado actual, o el prefijo asignado especificado si se proporciona `prefix`.|  
  
## Comentarios  
 La extensión de marcado `x:Type` tiene una función similar al operador `typeof()` en [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] o el operador `GetType` en [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].  
  
 La extensión de marcado `x:Type` proporciona un comportamiento de conversión de cadena para las propiedades que toman el tipo <xref:System.Type>.  La entrada es un tipo XAML.  La relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> es que la salida de <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> de la entrada <xref:System.Xaml.XamlType>, después de buscar el <xref:System.Xaml.XamlType> necesario basado en el contexto de esquema XAML y el servicio de <xref:System.Windows.Markup.IXamlTypeResolver> proporciona el contexto.  
  
 La clase <xref:System.Windows.Markup.TypeExtension> define el control para esta extensión de marcado en servicios XAML de .NET Framework.  
  
 En las implementaciones de marco específico, algunas propiedades que toman <xref:System.Type> como un valor pueden aceptar el nombre del tipo directamente \(el valor de cadena del tipo `Name`\).  Sin embargo, implementar este comportamiento es un escenario complejo.  Para obtener ejemplos, vea la sección "Notas de uso de WPF" que aparece a continuación.  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente.  Bajo el contexto de esquema XAML predeterminado para los servicios XAML de .NET Framework, que está basado en tipos CLR, el valor de este atributo es <xref:System.Reflection.MemberInfo.Name%2A> del tipo deseado, o bien contiene ese <xref:System.Reflection.MemberInfo.Name%2A> precedido por un prefijo para una asignación de espacio de nombres de XAML no predeterminado.  
  
 La extensión de marcado `x:Type` se puede usar en la sintaxis de elementos de objeto.  En este caso, es obligatorio especificar el valor de la propiedad <xref:System.Windows.Markup.TypeExtension.TypeName%2A> para inicializar correctamente la extensión.  
  
 La extensión de marcado `x:Type` se puede usar también como atributo detallado; sin embargo, este uso no es habitual: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## Notas de uso de WPF  
  
### Espacio de nombres XAML predeterminado y asignación de tipo  
 El espacio de nombres XAML predeterminado para programación de WPF contiene la mayoría de los tipos XAML que se necesitan para escenarios de XAML típicos; por consiguiente, a menudo se pueden evitar prefijos cuando se hace referencia a los valores de tipo de XAML.  Puede que sea necesario asignar un prefijo si se hace referencia a un tipo desde un ensamblado personalizado, o para los tipos que existen en un ensamblado de WPF pero que están dentro de un espacio de nombres CLR que no se ha asignado para formar parte de la definición de espacio de nombres XAML predeterminado.  Para obtener más información sobre prefijos, espacios de nombres XAML y cómo asignar espacios de nombres CLR, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### Escribir las propiedades que admitan el nombre de tipo como cadena  
 WPF admite técnicas que permiten especificar el valor de algunas propiedades de tipo<xref:System.Type> sin necesidad de un uso de extensión de marcado `x:Type`.  En su lugar, puede especificar el valor como una cadena que denomina el tipo.  Ejemplos de ello son <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=fullName> y <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>.  La compatibilidad para este comportamiento no se proporciona a través de convertidores de tipos o extensiones de marcado.  En su lugar, éste es un comportamiento del aplazamiento implementado a través de <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight admite una convención similar.  De hecho, Silverlight no admite actualmente `{x:Type}` en la compatibilidad con el lenguaje XAML, y no acepta el uso de `{x:Type}` fuera de algunas circunstancias pensadas para admitir la migración de XAML de Silverlight y de WPF.  Por consiguiente, el comportamiento de nombre de tipo como cadena se integra en toda evaluación de propiedades nativas de Silverlight donde el valor es un objeto <xref:System.Type>.  
  
## XAML 2009  
 XAML 2009 proporciona soporte adicional para los tipos genéricos, y modifica el comportamiento de característica de `x:TypeArguments` y `x:Type` para proporcionar este soporte.  
  
-   `x:TypeArguments` y el elemento de objeto asociado para la creación de instancias de un objeto genérico pueden estar en elementos distintos de la raíz.  Para obtener más información, vea la sección "XAML 2009" de [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 admite una sintaxis para especificar una restricción del tipo genérico en el marcado.  Esto lo puede utilizar `x:TypeArguments`, `x:Type` o las dos características en combinación.  
  
-   La implementación XAML de WPF al procesar XAML 2009 para la carga también agrega esta capacidad al comportamiento de la conversión de tipos implícita para ciertas propiedades de marco que utilizan el tipo <xref:System.Type>.  
  
 En WPF, puede utilizar características de XAML 2009, pero solo para XAML dinámico \(no compilado mediante marcado\).  El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten actualmente las palabras clave y características de XAML 2009.  
  
## Vea también  
 <xref:System.Windows.Style>   
 [Aplicar estilos y plantillas](../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)