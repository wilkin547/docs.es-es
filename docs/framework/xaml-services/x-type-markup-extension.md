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
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459918"
---
# <a name="xtype-markup-extension"></a>x:Type (Extensión de marcado)
Proporciona el objeto CLR <xref:System.Type> que es el tipo subyacente de un tipo XAML especificado.  
  
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
|`prefix`|Opcional. Prefijo que asigna un espacio de nombres XAML no predeterminado. No suele ser necesario especificar un prefijo. Vea la sección Comentarios.|  
|`typeNameValue`|Requerido. Un nombre de tipo que se pueda resolver en el espacio de nombres XAML predeterminado actual; o el prefijo asignado especificado si se proporciona `prefix`.|  
  
## <a name="remarks"></a>Comentarios  
 La extensión de marcado `x:Type` tiene una función similar al operador `typeof()` en C# o el operador `GetType` en Microsoft Visual Basic.  
  
 La extensión de marcado `x:Type` proporciona un comportamiento de conversión de cadena para las propiedades que toman el tipo <xref:System.Type>. La entrada es un tipo XAML. La relación entre el tipo XAML de entrada y el CLR de salida <xref:System.Type> es que el <xref:System.Type> de salida es el <xref:System.Xaml.XamlType.UnderlyingType%2A> de la <xref:System.Xaml.XamlType>de entrada, después de buscar el <xref:System.Xaml.XamlType> necesario basado en el contexto de esquema XAML y el servicio de <xref:System.Windows.Markup.IXamlTypeResolver> que proporciona el contexto.  
  
 En .NET Framework servicios XAML, el control de esta extensión de marcado se define mediante la clase <xref:System.Windows.Markup.TypeExtension>.  
  
 En implementaciones específicas de .NET Framework, algunas propiedades que toman <xref:System.Type> como valor pueden aceptar el nombre del tipo directamente (el valor de cadena del tipo `Name`). Sin embargo, la implementación de este comportamiento es un escenario complejo. Para obtener ejemplos, vea la sección "Notas de uso de WPF" que aparece a continuación.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente. En el contexto de esquema XAML predeterminado para .NET Framework servicios XAML, que se basa en tipos CLR, el valor de este atributo es el <xref:System.Reflection.MemberInfo.Name%2A> del tipo deseado o contiene ese <xref:System.Reflection.MemberInfo.Name%2A> precedido por un prefijo para una asignación de espacio de nombres XAML no predeterminada.  
  
 La extensión de marcado de `x:Type` se puede utilizar en la sintaxis de elementos de objeto. En este caso, es necesario especificar el valor de la propiedad <xref:System.Windows.Markup.TypeExtension.TypeName%2A> para inicializar correctamente la extensión.  
  
 La extensión de marcado `x:Type` también se puede usar como un atributo detallado; sin embargo, este uso no es típico: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Asignación de tipos y espacios de nombres XAML predeterminados  
 El espacio de nombres XAML predeterminado para la programación de WPF contiene la mayoría de los tipos XAML que necesita para escenarios XAML típicos; por lo tanto, a menudo se pueden evitar los prefijos al hacer referencia a valores de tipo XAML. Es posible que necesite asignar un prefijo si hace referencia a un tipo de un ensamblado personalizado o a tipos que existen en un ensamblado de WPF pero que proceden de un espacio de nombres CLR que no se ha asignado al espacio de nombres XAML predeterminado. Para obtener más información sobre los prefijos, los espacios de nombres XAML y la asignación de espacios de nombres CLR, vea [espacios de nombres y asignación de espacios de nombres XAML para WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Propiedades de tipo que admiten TypeName como cadena  
 WPF admite técnicas que permiten especificar el valor de algunas propiedades de tipo <xref:System.Type> sin requerir un uso de la extensión de marcado `x:Type`. En su lugar, puede especificar el valor como una cadena que nombra el tipo. Ejemplos de esto son <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> y <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. La compatibilidad con este comportamiento no se proporciona a través de convertidores de tipos o extensiones de marcado. En su lugar, se trata de un comportamiento de aplazamiento implementado a través de <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight admite una Convención similar. De hecho, Silverlight no admite actualmente `{x:Type}` en su compatibilidad con el lenguaje XAML y no acepta `{x:Type}` usos fuera de algunas circunstancias que están diseñadas para admitir la migración XAML de WPF-Silverlight. Por lo tanto, el comportamiento de tipo TypeName como cadena está integrado en todas las evaluaciones de propiedades nativas de Silverlight, donde un <xref:System.Type> es el valor.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 proporciona compatibilidad adicional para tipos genéricos y modifica el comportamiento de las características de `x:TypeArguments` y `x:Type` para proporcionar esta compatibilidad.  
  
- `x:TypeArguments` y el elemento de objeto asociado para una creación de instancias de objeto genérico pueden estar en elementos distintos de la raíz. Para obtener más información, vea la sección "XAML 2009" de [la Directiva x:TypeArguments](x-typearguments-directive.md).  
  
- XAML 2009 admite una sintaxis para especificar una restricción de tipo genérico en el marcado. Lo pueden usar `x:TypeArguments`, `x:Type`o las dos características en combinación.  
  
- La implementación XAML de WPF cuando se procesa XAML 2009 para la carga también agrega esta funcionalidad al comportamiento de conversión de tipos implícito para ciertas propiedades de .NET Framework que usan el tipo <xref:System.Type>.  
  
 En WPF, puede usar las características de XAML 2009, pero solo para XAML dinámico (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Style>
- [Aplicar estilos y plantillas](../wpf/controls/styling-and-templating.md)
- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
