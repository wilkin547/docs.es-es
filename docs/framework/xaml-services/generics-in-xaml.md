---
title: Elementos genéricos en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9263edf18872f510f5f2f4e3e9cb793e45c5d0b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954107"
---
# <a name="generics-in-xaml"></a>Elementos genéricos en XAML
Los servicios de XAML de .NET Framework implementados en System.Xaml proporciona compatibilidad para utilizar tipos genéricos de CLR. Esta compatibilidad incluye especificar las restricciones de los genéricos como un argumento de tipo y exigir la restricción llamando adecuado `Add` método para casos de colección genéricos. En este tema se describe aspectos del uso y que hacen referencia a tipos genéricos en XAML.  
  
## <a name="xtypearguments"></a>x:TypeArguments  
 `x:TypeArguments` es una directiva definida por el lenguaje XAML. Cuando se utiliza como un miembro de un tipo XAML que está respaldado por un tipo genérico, `x:TypeArguments` pasa restringir argumentos de la clase genérica para el constructor de copia de seguridad de tipo. Para la sintaxis de referencia que pertenece a los servicios XAML de .NET Framework el uso de `x:TypeArguments`, que incluye ejemplos de sintaxis, vea [x: TypeArguments Directive](x-typearguments-directive.md).  
  
 Dado que `x:TypeArguments` toma una cadena y tiene el respaldo de convertidor de tipo, normalmente se declara en el uso XAML como un atributo.  
  
 En el flujo de nodo XAML, la información se declara mediante `x:TypeArguments` pueden obtenerse <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> en un `StartObject` posición en el flujo de nodo. El valor devuelto de <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> es una lista de <xref:System.Xaml.XamlType> valores. Determinación de si un tipo XAML representa un tipo genérico puede realizarse mediante una llamada a <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Reglas y convenciones de sintaxis para tipos genéricos en XAML  
 En XAML, siempre se debe representar un tipo genérico como un genérico restringido; un genérico sin restricciones nunca está presente en el sistema de tipos XAML o un flujo de nodo XAML y no se puede representar en el marcado XAML. Se puede hacer referencia a un tipo genérico dentro de la sintaxis de atributo XAML, para los casos donde es una restricción de tipo anidado de un tipo genérico que se hace referencia por `x:TypeArguments`, o para los casos donde `x:Type` proporciona una referencia de tipo CLR para un tipo genérico. Esto se admite a través de la <xref:System.Xaml.Schema.XamlTypeTypeConverter> clase definida por los servicios XAML de .NET Framework.  
  
 El XAML habilitarlo el formato de sintaxis de atributo <xref:System.Xaml.Schema.XamlTypeTypeConverter> modifica el típico MSIL / corchetes para tipos y las restricciones de los genéricos de convención de sintaxis CLR que utiliza el ángulo y en su lugar sustituye los paréntesis para el contenedor de restricción. Para obtener un ejemplo, vea [x: TypeArguments Directive](x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Genéricos y las características de XAML 2009  
 Si utiliza XAML 2009 en lugar de asignación de CLR de tipos para obtener tipos XAML para primitivas del lenguaje común base, puede usar [tipos integrados de XAML 2009](built-in-types-for-common-xaml-language-primitives.md) como elementos de información en `x:TypeArguments`. Por ejemplo, podría declarar la siguiente (prefijo asignaciones no se muestra, pero `x` es el espacio de nombres XAML XAML del lenguaje XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Compatibilidad con los genéricos en WPF y otros marcos de trabajo v3.5  
 Para el uso de XAML 2006 destinado específicamente a WPF, [x: Class](x-class-directive.md) también debe proporcionarse en el mismo elemento que `x:TypeArguments`, y ese elemento debe ser el elemento raíz en un documento XAML. El elemento raíz debe asignar a un tipo genérico con al menos un argumento de tipo. Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Posibles soluciones para admitir los usos de genéricos incluyen definir una extensión de marcado personalizada que puede devolver tipos genéricos o proporcionar un ajuste de la definición que se deriva de un tipo genérico pero aplana la restricción en su propia definición de clase genérica de la clase.  
  
 En WPF y de destino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], puede usar las características de XAML 2009 junto con `x:TypeArguments`, pero solo para XAML flexible (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 Flujos de trabajo personalizados en Windows Workflow Foundation para [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] no admiten el uso XAML genérico.  
  
## <a name="see-also"></a>Vea también

- [x:TypeArguments (Directiva)](x-typearguments-directive.md)
- [x:Class (Directiva)](x-class-directive.md)
- [Tipos integrados para primitivas comunes en el lenguaje XAML](built-in-types-for-common-xaml-language-primitives.md)
