---
title: "Cómo: Comparar cadenas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4837fa57c962cba841ffcc83c5bd4475a4faff0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compare-strings-c-programming-guide"></a>Cómo: Comparar cadenas (Guía de programación de C#)

Cuando se comparan cadenas, se genera un resultado que indica que una cadena es mayor o menor que otra, o que las dos cadenas son iguales. Las reglas por las que se determina el resultado son diferentes en función de si se realiza una *comparación ordinal* o una *comparación dependiente de la referencia cultural*. Es importante usar el tipo correcto de comparación para la tarea.

 Use las comparaciones ordinales básicas cuando tenga que comparar u ordenar los valores de dos cadenas sin tener en cuenta las convenciones lingüísticas. Una comparación ordinal básica (`System.StringComparison.Ordinal`) distingue mayúsculas de minúsculas, lo que significa que las dos cadenas deben coincidir carácter por carácter: "and" no es igual a "And" o "AND". Una variación usada con frecuencia es `System.StringComparison.OrdinalIgnoreCase`, que hará que "and", "And" y "AND" coincidan. `StringComparison.OrdinalIgnoreCase` se suele usar para comparar nombres de archivo, nombres de ruta de acceso, rutas de acceso de red y cualquier otra cadena cuyo valor no cambie según la configuración regional del equipo del usuario. Para obtener más información, consulta <xref:System.StringComparison?displayProperty=nameWithType>.

 Las comparaciones dependientes de la referencia cultural suelen usarse para comparar y ordenar cadenas introducidas por los usuarios finales, ya que los caracteres y las convenciones de ordenación de estas cadenas pueden variar según la configuración regional del equipo del usuario. Incluso las cadenas que contienen caracteres idénticos podrían ordenarse de forma diferente en función de la referencia cultural del subproceso actual.

> [!NOTE]
> Cuando se comparan cadenas, debe usar los métodos que especifican explícitamente el tipo de comparación que va a realizar. Esto hace que el código sea mucho más legible y fácil de mantener. Siempre que sea posible, use las sobrecargas de los métodos de las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Array?displayProperty=nameWithType> que toman un parámetro de enumeración <xref:System.StringComparison>, de manera que pueda especificar qué tipo de comparación se va a realizar. Es mejor evitar el uso de los operadores `==` y `!=` cuando se comparan cadenas. Además, evite el uso de métodos de instancia <xref:System.String.CompareTo%2A?displayProperty=nameWithType> porque ninguna de las sobrecargas toma un <xref:System.StringComparison>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo comparar correctamente cadenas cuyos valores no cambiarán en función de la configuración regional del equipo del usuario. Además, también se muestra la característica de C# de *internamiento de cadenas*. Cuando un programa declara dos o más variables de cadena idénticas, el compilador lo almacena todo en la misma ubicación. Mediante una llamada al método <xref:System.Object.ReferenceEquals%2A>, puede ver que las dos cadenas realmente hacen referencia al mismo objeto en memoria. Use el método <xref:System.String.Copy%2A?displayProperty=nameWithType> para evitar el internamiento, como se muestra en el ejemplo.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra cómo comparar cadenas de la mejor manera con los métodos <xref:System.String?displayProperty=nameWithType> que toman una enumeración <xref:System.StringComparison>. Tenga en cuenta que los métodos de instancia <xref:System.String.CompareTo%2A?displayProperty=nameWithType> no se usan aquí, porque ninguna de las sobrecargas toma un <xref:System.StringComparison>.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo ordenar y buscar cadenas en una matriz de una manera dependiente de la referencia cultural mediante los métodos estáticos <xref:System.Array> que toman un parámetro <xref:System.StringComparer?displayProperty=nameWithType>.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Las clases de colección como <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> y <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> tienen constructores que toman un parámetro <xref:System.StringComparer?displayProperty=nameWithType> cuando el tipo de los elementos o claves es `string`. En general, debe usar estos constructores siempre que sea posible y especificar `Ordinal` u `OrdinalIgnoreCase`.

## <a name="see-also"></a>Vea también
 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>  
 <xref:System.StringComparer?displayProperty=nameWithType>  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)  
 [Comparar cadenas](../../../standard/base-types/comparing.md)  
 [Globalizar y localizar aplicaciones](/visualstudio/ide/globalizing-and-localizing-applications)