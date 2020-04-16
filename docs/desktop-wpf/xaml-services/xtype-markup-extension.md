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
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432639"
---
# <a name="xtype-markup-extension"></a>x:Type (Extensión de marcado)

Proporciona el <xref:System.Type> objeto CLR que es el tipo subyacente para un tipo XAML especificado.

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
|`prefix`|Opcional. Prefijo que asigna un espacio de nombres XAML no predeterminado. La especificación de un prefijo no suele ser necesaria. Vea la sección Comentarios.|
|`typeNameValue`|Necesario. Un nombre de tipo que se puede resolver en el espacio de nombres XAML predeterminado actual; o el prefijo asignado `prefix` especificado si se proporciona.|

## <a name="remarks"></a>Observaciones

La `x:Type` extensión de marcado tiene `typeof()` una función `GetType` similar al operador en C- o el operador en Microsoft Visual Basic.

La `x:Type` extensión de marcado proporciona un comportamiento de conversión de cadena de tipo para las propiedades que toman el tipo <xref:System.Type>. La entrada es un tipo XAML. La relación entre el tipo XAML <xref:System.Type> de entrada <xref:System.Type> y <xref:System.Xaml.XamlType.UnderlyingType%2A> el <xref:System.Xaml.XamlType>CLR de salida <xref:System.Xaml.XamlType> es que la salida <xref:System.Windows.Markup.IXamlTypeResolver> es la de la entrada, después de buscar lo necesario en función del contexto de esquema XAML y el servicio que proporciona el contexto.

En los servicios XAML de .NET, la <xref:System.Windows.Markup.TypeExtension> clase define el control de esta extensión de marcado.

En implementaciones específicas del <xref:System.Type> marco de trabajo, algunas propiedades que toman como `Name`un valor pueden aceptar el nombre del tipo directamente (el valor de cadena del tipo ). Sin embargo, implementar este comportamiento es un escenario complejo. Para obtener ejemplos, vea la sección "Notas de uso de WPF" que se muestra a continuación.

La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente. En el contexto de esquema XAML predeterminado para los servicios XAML de .NET, <xref:System.Reflection.MemberInfo.Name%2A> que se basa en <xref:System.Reflection.MemberInfo.Name%2A> tipos CLR, el valor de este atributo es el del tipo deseado o contiene el precedido por un prefijo para una asignación de espacio de nombres XAML no predeterminada.

La `x:Type` extensión de marcado se puede utilizar en la sintaxis de elemento de objeto. En este caso, es necesario <xref:System.Windows.Markup.TypeExtension.TypeName%2A> especificar el valor de la propiedad para inicializar correctamente la extensión.

La `x:Type` extensión de marcado también se puede utilizar como un atributo detallado; sin embargo, este uso no es típico:`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

### <a name="default-xaml-namespace-and-type-mapping"></a>Asignación de tipos y espacio de nombres XAML predeterminado

El espacio de nombres XAML predeterminado para la programación DE WPF contiene la mayoría de los tipos XAML que necesita para escenarios XAML típicos; por lo tanto, a menudo puede evitar prefijos al hacer referencia a valores de tipo XAML. Es posible que deba asignar un prefijo si hace referencia a un tipo de un ensamblado personalizado o para los tipos que existen en un ensamblado WPFWPF pero proceden de un espacio de nombres CLR que no se ha asignado al espacio de nombres XAML predeterminado. Para obtener más información acerca de los prefijos, los espacios de nombres XAML y la asignación de espacios de nombres CLR, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF .

### <a name="type-properties-that-support-typename-as-string"></a>Propiedades de tipo que admiten Typename-as-String

WPFWPF admite técnicas que permiten especificar <xref:System.Type> el valor `x:Type` de algunas propiedades de tipo sin necesidad de un uso de extensión de marcado. En su lugar, puede especificar el valor como una cadena que nombra el tipo. Ejemplos de <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> esto <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>son y . La compatibilidad con este comportamiento no se proporciona a través de convertidores de tipos o extensiones de marcado. En su lugar, se trata de <xref:System.Windows.FrameworkElementFactory>un comportamiento de aplazamiento implementado a través de .

Silverlight admite una convención similar. De hecho, Silverlight no `{x:Type}` admite actualmente su compatibilidad `{x:Type}` con el lenguaje XAML y no acepta usos fuera de algunas circunstancias que están diseñadas para admitir la migración XAML de WPF-Silverlight. Por lo tanto, el comportamiento typename-as-string está integrado en <xref:System.Type> toda la evaluación de propiedades nativas de Silverlight donde a es el valor.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 proporciona compatibilidad adicional para tipos genéricos y modifica el comportamiento de las características de `x:TypeArguments` y `x:Type` para proporcionar esta compatibilidad.

- `x:TypeArguments`y el elemento de objeto asociado para una instancia de objeto genérico puede estar en elementos distintos de la raíz. Para obtener más información, vea la sección "XAML 2009" de [x:TypeArguments Directive](xtypearguments-directive.md).

- XAML 2009 admite una sintaxis para especificar la restricción de un tipo genérico en el marcado. Esto puede ser `x:TypeArguments`utilizado `x:Type`por , por , o por las dos características en combinación.

- La implementación de XAML de WPF al procesar XAML 2009 para carga también <xref:System.Type>agrega esta capacidad al comportamiento de conversión de tipos implícito para determinadas propiedades de marco de trabajo que usan tipo .

En WPFWPF, puede usar las características de XAML 2009, pero solo para XAML suelto (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Style>
- [Aplicar estilos y plantillas](../fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
