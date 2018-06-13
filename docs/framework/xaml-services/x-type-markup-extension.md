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
ms.openlocfilehash: d3731a5249788b509c48623d8fa2284541f996ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563125"
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
|`prefix`|Opcional. Prefijo que se asigna un espacio de nombres XAML no predeterminado. Especificar un prefijo con frecuencia no es necesario. Vea la sección Comentarios.|  
|`typeNameValue`|Requerido. Un nombre de tipo que se puede resolver en nombres XAML predeterminado actual; o especificado asigna prefijo si `prefix` se proporciona.|  
  
## <a name="remarks"></a>Comentarios  
 El `x:Type` extensión de marcado tiene una función similar a la `typeof()` operador de C# o `GetType` (operador) en Microsoft Visual Basic.  
  
 El `x:Type` extensión de marcado proporciona un comportamiento de conversión de cadena para las propiedades que tenga el tipo <xref:System.Type>. La entrada es un tipo XAML. La relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> que es el resultado <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> de la entrada <xref:System.Xaml.XamlType>, después de buscar el necesario <xref:System.Xaml.XamlType> basándose en el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver>proporciona el contexto de servicio.  
  
 En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.TypeExtension> clase.  
  
 En las implementaciones de un marco concreto, algunas propiedades que toman <xref:System.Type> como un valor puede aceptar el nombre del tipo directamente (el valor de cadena del tipo `Name`). Sin embargo, implementar este comportamiento es un escenario complejo. Para obtener ejemplos, vea la sección "Notas de uso de WPF" que sigue.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente. En el contexto de esquema XAML predeterminado para servicios de XAML de .NET Framework, que se basa en tipos CLR, el valor de este atributo es el <xref:System.Reflection.MemberInfo.Name%2A> del tipo deseado, o que contiene <xref:System.Reflection.MemberInfo.Name%2A> precedido por un prefijo para un espacio de nombres XAML no predeterminado asignación.  
  
 El `x:Type` en la sintaxis de elemento de objeto, se puede utilizar la extensión de marcado. En este caso, especificando el valor de la <xref:System.Windows.Markup.TypeExtension.TypeName%2A> propiedad es necesaria para inicializar correctamente la extensión.  
  
 El `x:Type` extensión de marcado también puede usarse como un atributo detallado; sin embargo este uso no es habitual: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Namespace XAML y asignación de tipos predeterminados  
 Espacio de nombres XAML predeterminado para la programación de WPF contiene la mayoría de los tipos XAML que necesario para los escenarios típicos de XAML; por lo tanto, se pueden evitar a menudo los prefijos al hacer referencia a valores de tipo XAML. Debe asignar un prefijo si hace referencia a un tipo de un ensamblado personalizado o para los tipos que existen en un ensamblado WPF pero proceden de un espacio de nombres CLR que no se ha asignado al espacio de nombres XAML predeterminado. Para obtener más información acerca de los prefijos y espacios de nombres XAML, los espacios de nombres CLR de asignación, consulte [espacios de nombres XAML y asignación de Namespace para XAML de WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Propiedades esa compatibilidad Typename como cadena de tipo  
 WPF admite técnicas que permiten especificar el valor de algunas propiedades de tipo <xref:System.Type> sin necesidad de un `x:Type` uso de la extensión de marcado. En su lugar, puede especificar el valor como una cadena que designa el tipo. Ejemplos de esto son <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> y <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Compatibilidad con este comportamiento no se proporciona a través de las extensiones de marcado o los convertidores de tipos. En su lugar, esto es un comportamiento del aplazamiento implementado a través de <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight admite la convención similar. De hecho, Silverlight no admite actualmente la `{x:Type}` en su compatibilidad de lenguaje XAML y no acepta `{x:Type}` usos fuera algunas circunstancias que están diseñados para admitir la migración de XAML de WPF y Silverlight. Por lo tanto, el comportamiento de typename como cadena está integrado para la evaluación de propiedades nativas de Silverlight todos los donde un <xref:System.Type> es el valor.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 proporciona compatibilidad adicional para tipos de genéricos y modifica el comportamiento de la característica de `x:TypeArguments` y `x:Type` para proporcionar esta compatibilidad.  
  
-   `x:TypeArguments` y el elemento de objeto asociado para la creación de instancias de un objeto genérico puede estar en elementos distintos de la raíz. Para obtener más información, vea la sección "XAML 2009" de [x: TypeArguments (directiva)](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 admite una sintaxis para especificar la restricción de un tipo genérico en el marcado. Esto se puede utilizar por `x:TypeArguments`, `x:Type`, o las dos características en combinación.  
  
-   Implementación de XAML de WPF al procesar XAML 2009 para carga también agrega esta capacidad para el comportamiento de conversión de tipos implícita para ciertas propiedades de marco de trabajo que utilizan tipo <xref:System.Type>.  
  
 En WPF, puede usar características de XAML 2009 pero solo para XAML dinámico (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Style>  
 [Aplicar estilos y plantillas](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
