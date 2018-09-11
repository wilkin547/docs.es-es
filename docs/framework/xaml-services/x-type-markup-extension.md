---
title: x:Type (Extensión de marcado)
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: e4d56c5b5deda0bd1df8827020e0b76cc6276c1c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44273971"
---
# <a name="xtype-markup-extension"></a>x:Type (Extensión de marcado)
Proporciona el CLR <xref:System.Type> objeto que es el tipo subyacente para un tipo XAML especificado.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`prefix`|Opcional. Un prefijo que se asigna un espacio de nombres XAML no predeterminado. Especificar un prefijo con frecuencia no es necesario. Vea la sección Comentarios.|  
|`typeNameValue`|Requerido. Un nombre de tipo en nombres XAML predeterminado actual; o asignado especificado prefijo si `prefix` proporcionado.|  
  
## <a name="remarks"></a>Comentarios  
 El `x:Type` extensión de marcado cuya función sea similar a la `typeof()` operador en C# o la `GetType` operador en Microsoft Visual Basic.  
  
 El `x:Type` extensión de marcado proporciona un comportamiento de conversión de cadena para las propiedades que toman el tipo <xref:System.Type>. La entrada es un tipo XAML. La relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> es que la salida <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> de la entrada <xref:System.Xaml.XamlType>, después de buscar el necesario <xref:System.Xaml.XamlType> según el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver>proporciona el contexto de servicio.  
  
 En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.TypeExtension> clase.  
  
 En las implementaciones de un marco concreto, algunas propiedades que toman <xref:System.Type> como un valor puede aceptar el nombre del tipo directamente (el valor de cadena del tipo `Name`). Sin embargo, al implementar este comportamiento es un escenario complejo. Para obtener ejemplos, vea la sección "Notas de uso de WPF" a continuación.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente. En el contexto de esquema XAML predeterminado para los servicios de XAML de .NET Framework, que se basa en tipos CLR, el valor de este atributo es el <xref:System.Reflection.MemberInfo.Name%2A> del tipo deseado, o que contiene <xref:System.Reflection.MemberInfo.Name%2A> precedido por un prefijo para un espacio de nombres XAML no predeterminado la asignación.  
  
 El `x:Type` se puede usar la extensión de marcado en la sintaxis de elemento de objeto. En este caso, especificando el valor de la <xref:System.Windows.Markup.TypeExtension.TypeName%2A> propiedad es necesaria para inicializar correctamente la extensión.  
  
 El `x:Type` también se puede usar extensión de marcado como un atributo detallado; pero este uso no es típico: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>XAML Namespace y asignación de tipos predeterminados  
 Espacio de nombres XAML predeterminado para la programación de WPF contiene la mayoría de los tipos XAML que necesita para los escenarios típicos de XAML; por lo tanto, puede evitar a menudo los prefijos al hacer referencia a los valores de tipo XAML. Es posible que deba asignar un prefijo si hacen referencia a un tipo de un ensamblado personalizado o para los tipos que existen en un ensamblado de WPF, pero son de un espacio de nombres CLR que no se ha asignado al espacio de nombres XAML predeterminado. Para obtener más información acerca de los prefijos de espacios de nombres XAML y asignar espacios de nombres CLR, vea [los espacios de nombres XAML y la asignación de Namespace para WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Escriba las propiedades de esa compatibilidad Typename como cadena  
 WPF admite las técnicas que permiten especificar el valor de algunas propiedades de tipo <xref:System.Type> sin necesidad de un `x:Type` uso de la extensión de marcado. En su lugar, puede especificar el valor como una cadena que nombra el tipo. Algunos ejemplos son <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> y <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. No se proporciona soporte técnico para este comportamiento a través de los convertidores de tipos o extensiones de marcado. En su lugar, esto es un comportamiento de aplazamiento que se implementan a través de <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight admite una convención similar. De hecho, Silverlight no admite actualmente `{x:Type}` en su compatibilidad de lenguaje XAML y no acepta `{x:Type}` usos fuera algunas circunstancias que están diseñados para admitir la migración de XAML de WPF y Silverlight. Por lo tanto, el comportamiento de la cadena como typename está integrado a la evaluación de propiedades nativas de Silverlight todos los donde un <xref:System.Type> es el valor.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 proporciona compatibilidad adicional para tipos de genéricos y modifica el comportamiento de la característica de `x:TypeArguments` y `x:Type` proporcionar este soporte técnico.  
  
-   `x:TypeArguments` y puede ser el elemento de objeto asociado para la creación de instancias de un objeto genérico en los elementos que no sea la raíz. Para obtener más información, consulte la sección "XAML 2009" de [x: TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 admite una sintaxis para especificar la restricción de un tipo genérico en el marcado. Esto puede usarse por `x:TypeArguments`, por `x:Type`, o las dos características en combinación.  
  
-   Implementación de WPF XAML cuando el procesamiento de XAML 2009 de carga también agrega esta funcionalidad para el comportamiento de conversión de tipos implícita para ciertas propiedades de marco de trabajo que utilizan el tipo <xref:System.Type>.  
  
 En WPF, puede usar las características de XAML 2009 pero solo para XAML flexible (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Style>  
 [Aplicar estilos y plantillas](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
