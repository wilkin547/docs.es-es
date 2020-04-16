---
title: Elementos genéricos en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432963"
---
# <a name="generics-in-xaml"></a>Elementos genéricos en XAML

Servicios XAML de .NET <xref:System.Xaml?displayProperty=fullName> tal como se implementan en proporciona compatibilidad para el uso de tipos CLR genéricos. Esta compatibilidad incluye especificar las restricciones de genéricos como un argumento `Add` de tipo y aplicar la restricción mediante una llamada al método adecuado para casos de recopilación genéricos. En este tema se describen aspectos del uso y la referencia a tipos genéricos en XAML.

## <a name="xtypearguments"></a>x:TypeArguments

`x:TypeArguments`es una directiva definida por el lenguaje XAML. Cuando se usa como miembro de un tipo XAML respaldado `x:TypeArguments` por un tipo genérico, pasa argumentos de tipo de restricción del genérico al constructor de respaldo. Para obtener una sintaxis de referencia `x:TypeArguments`que pertenece al uso de servicios XAML de .NET , que incluye ejemplos de sintaxis, vea [directiva x:TypeArguments](xtypearguments-directive.md).

Dado `x:TypeArguments` que toma una cadena y tiene respaldo de convertidor de tipos, normalmente se declara en el uso XAML como un atributo.

En el flujo de nodo XAML, la información declarada por `x:TypeArguments` se puede obtener en <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> una `StartObject` posición en el flujo de nodo. El valor <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> devuelto de <xref:System.Xaml.XamlType> es una lista de valores. Determinación de si un tipo XAML representa un <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>tipo genérico mediante una llamada a .

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Reglas y convenciones de sintaxis para genéricos en XAML

En XAML, un tipo genérico siempre debe representarse como un genérico restringido. Un genérico sin restricciones nunca está presente en el sistema de tipos XAML o un flujo de nodo XAML y no se puede representar en el marcado XAML. Se puede hacer referencia a un genérico dentro de la sintaxis de `x:TypeArguments`atributo XAML `x:Type` para los casos en los que es una restricción de tipo anidado de un genérico al que hace referencia , o para los casos en los que proporciona una referencia de tipo CLR para un tipo genérico. Hacer referencia a genéricos <xref:System.Xaml.Schema.XamlTypeTypeConverter> se admite a través de la clase definida por los servicios XAML de .NET.

El formulario de sintaxis <xref:System.Xaml.Schema.XamlTypeTypeConverter> de atributo XAML habilitado mediante modifica la convención de sintaxis típica de MSIL / CLR que usa corchetes angulares para tipos y restricciones de genéricos y, en su lugar, sustituye los paréntesis para el contenedor de restricciones. Para obtener un ejemplo, vea [directiva x:TypeArguments](xtypearguments-directive.md).

## <a name="generics-and-xaml-2009-features"></a>Características de genéricos y XAML 2009

Si usa XAML 2009 en lugar de asignar los tipos base de CLR para obtener tipos XAML para primitivas `x:TypeArguments`de lenguaje común, puede usar tipos integrados de [XAML 2009](types-for-primitives.md) como elementos de información en . Por ejemplo, podría declarar lo siguiente (no `x` se muestran las asignaciones de prefijo, pero es el espacio de nombres XAML del lenguaje XAML para XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>Compatibilidad con genéricos en WPFWPF

Para el uso de XAML 2006 cuando se dirige específicamente WPFWPF, [x:Class](xclass-directive.md) también debe proporcionarse en el mismo elemento que `x:TypeArguments`, y ese elemento debe ser el elemento raíz de un documento XAML. El elemento raíz debe asignarse a un tipo genérico con al menos un argumento de tipo. Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>.

Las posibles soluciones para admitir usos genéricos incluyen la definición de una extensión de marcado personalizada que puede devolver tipos genéricos o proporcionar una definición de clase de ajuste que deriva de un tipo genérico pero acopla la restricción genérica en su propia definición de clase.

En WPFWPF puede usar las características `x:TypeArguments`de XAML 2009 junto con , pero solo para XAML suelto (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.

Los flujos de trabajo personalizados en Windows Workflow Foundation para .NET Framework 3.5 no admiten el uso de XAML genérico.

## <a name="see-also"></a>Consulte también

- [x:TypeArguments (Directiva)](xtypearguments-directive.md)
- [x:Class (Directiva)](xclass-directive.md)
- [Tipos integrados para primitivas comunes en el lenguaje XAML](types-for-primitives.md)
