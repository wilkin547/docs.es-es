---
title: "Elementos genéricos en XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c0e5bfb4f327028f09e8c898cf07e5fec9a5f789
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="generics-in-xaml"></a>Elementos genéricos en XAML
Los servicios de XAML de .NET Framework implementados en System.Xaml proporciona compatibilidad para utilizar tipos genéricos de CLR. Esta compatibilidad incluye especificar las restricciones de los genéricos como un argumento de tipo y exigir la restricción mediante una llamada a la correspondiente `Add` método para casos de colección genéricos. Este tema describe aspectos del uso y hacer referencia a tipos genéricos en XAML.  
  
## <a name="xtypearguments"></a>x: TypeArguments  
 `x:TypeArguments`es una directiva definida por el lenguaje XAML. Cuando se utiliza como un miembro de un tipo XAML que está respaldado por un tipo genérico, `x:TypeArguments` pasa si se restringen los argumentos de la clase genérica para el constructor de copias de seguridad de tipo. Para la sintaxis de referencia que pertenece a los servicios XAML de .NET Framework el uso de `x:TypeArguments`, que incluye ejemplos de sintaxis, vea [x: TypeArguments (directiva)](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Dado que `x:TypeArguments` toma una cadena y tiene copias de seguridad de convertidor de tipo, normalmente se declara en el uso XAML como un atributo.  
  
 En el flujo de nodo XAML, la información se declara mediante `x:TypeArguments` puede obtenerse de <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> en un `StartObject` posición en el flujo de nodo. El valor devuelto de <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> es una lista de <xref:System.Xaml.XamlType> valores. Determinación de si un tipo XAML representa un tipo genérico puede realizarse mediante una llamada a <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Reglas y convenciones de sintaxis para tipos genéricos en XAML  
 En XAML, un tipo genérico siempre debe representarse como un tipo genérico restringido; un genérico sin restricciones nunca está presente en el sistema de tipos XAML o un flujo de nodo XAML y no se puede representar en el marcado XAML. Un tipo genérico puede hacer referencia en la sintaxis de atributo XAML, para los casos donde es una restricción de tipo anidado de un tipo genérico al que hace referencia `x:TypeArguments`, o en los casos donde `x:Type` proporciona una referencia de tipo CLR para un tipo genérico. Esto se admite a través de la <xref:System.Xaml.Schema.XamlTypeTypeConverter> clase definida por los servicios XAML de .NET Framework.  
  
 El código XAML habilitado por el formato de sintaxis de atributo <xref:System.Xaml.Schema.XamlTypeTypeConverter> modifica el código MSIL típico / corchetes para tipos y las restricciones de los genéricos de convención de la sintaxis CLR que usa el ángulo y en su lugar sustituye los paréntesis para el contenedor de restricción. Para obtener un ejemplo, vea [x: TypeArguments (directiva)](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Genéricos y características de XAML 2009  
 Si utiliza XAML 2009 en lugar de asignar el CLR de tipos para obtener tipos XAML para los primitivos del lenguaje común base, puede usar [tipos integrados de XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) como elementos de información en `x:TypeArguments`. Por ejemplo, podría declarar lo siguiente (prefijo asignaciones no se muestra, pero `x` es el espacio de nombres XAML del lenguaje XAML para XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Compatibilidad con los genéricos en WPF y otros marcos v3.5  
 Para el uso de XAML 2006 destinado específicamente a WPF, [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar en el mismo elemento que `x:TypeArguments`, y ese elemento debe ser el elemento raíz en un documento XAML. El elemento raíz debe asignar a un tipo genérico con al menos un argumento de tipo. Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Posibles soluciones para admitir usos genéricos incluyen definir una extensión de marcado personalizada que puede devolver tipos genéricos o proporcionar un ajuste de definición que se deriva de un tipo genérico, pero reduce la restricción en su propia definición de clase genérica de la clase.  
  
 En WPF y destino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], puede usar las características de XAML 2009 junto con `x:TypeArguments`, pero solo para XAML dinámico (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 Flujos de trabajo personalizados en [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] para [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] no admiten el uso XAML genérico.  
  
## <a name="see-also"></a>Vea también  
 [x:TypeArguments (Directiva)](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [x:Class (Directiva)](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Tipos integrados para primitivas comunes en el lenguaje XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
