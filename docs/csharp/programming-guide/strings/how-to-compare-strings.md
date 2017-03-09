---
title: "C&#243;mo: Comparar cadenas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "comparar cadenas [C#]"
  - "cadenas [C#], comparación"
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# C&#243;mo: Comparar cadenas (Gu&#237;a de programaci&#243;n de C#)
Cuando se comparan cadenas, se genera un resultado que indica que una cadena es mayor o menor que otra o que las dos cadenas son iguales.  Las reglas por las que se determina el resultado son distintas dependiendo de que se realice una *comparación ordinal* o una *comparación dependiente de la referencia cultural*.  Es importante utilizar el tipo correcto de comparación para cada tarea concreta.  
  
 Utilice comparaciones ordinales básicas cuando tenga que comparar u ordenar los valores de dos cadenas sin tener en cuenta las convenciones lingüísticas.  Una comparación ordinal básica \(`System.StringComparison.Ordinal`\) distingue entre mayúsculas y minúsculas, lo que significa que las dos cadenas deben coincidir carácter por carácter: "and" no es igual que "And" o "AND".  Una variación utilizada con frecuencia es `System.StringComparison.OrdinalIgnoreCase`, que coincidirá con "and" "And" y "AND".  `StringComparison.OrdinalIgnoreCase` se suele usar para comparar nombres de archivo, nombres de ruta de acceso, rutas de red y cualquier otra cadena cuyo valor no cambie en función de la configuración regional del equipo del usuario.  Para obtener más información, vea <xref:System.StringComparison?displayProperty=fullName>.  
  
 Las comparaciones dependientes de la referencia cultural se utilizan normalmente para comparar y ordenar cadenas especificadas por usuarios finales, ya que los caracteres y las convenciones de ordenación de estas cadenas pueden variar dependiendo de la configuración regional del equipo del usuario.  Incluso las cadenas que contienen caracteres idénticos pueden ordenarse de forma distinta dependiendo de la referencia cultural del subproceso actual.  
  
> [!NOTE]
>  Al comparar cadenas, debe utilizar los métodos que especifican explícitamente el tipo de comparación que desea realizar.  Esto hace que su código sea mucho más fácil de mantener y leer.  Siempre que sea posible, utilice las sobrecargas de los métodos de las clases <xref:System.String?displayProperty=fullName> y <xref:System.Array?displayProperty=fullName> que toman un parámetro de enumeración <xref:System.StringComparison>, de forma que pueda especificar qué tipo de comparación se va a realizar.  Es conveniente evitar el uso de los operadores `==` y `!=` al comparar cadenas.  Asimismo, evite utilizar los métodos de instancia <xref:System.String.CompareTo%2A?displayProperty=fullName>, ya que ninguna de las sobrecargas toma un elemento <xref:System.StringComparison>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo comparar correctamente las cadenas cuyos valores no cambiarán en función de la configuración regional del equipo del usuario.  Además, también muestra la característica *asignación al grupo interno de cadenas* de C\#.  Cuando un programa declara dos o más variables de cadena idénticas, el compilador las almacena en la misma ubicación.  Al llamar al método <xref:System.Object.ReferenceEquals%2A>, puede ver que las dos cadenas hacen referencia realmente al mismo objeto en memoria.  Utilice el método <xref:System.String.Copy%2A?displayProperty=fullName> para evitar el proceso de asignación al grupo interno de cadenas, como se muestra en el ejemplo.  
  
 [!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#11)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo comparar cadenas de la mejor forma utilizando los métodos <xref:System.String?displayProperty=fullName> que toman una enumeración <xref:System.StringComparison>.  Tenga en cuenta que aquí no se utilizan los métodos de instancia<xref:System.String.CompareTo%2A?displayProperty=fullName>, ya que ninguna de las sobrecargas toma un elemento <xref:System.StringComparison>.  
  
 [!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#31)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo ordenar y buscar cadenas en una matriz de forma que se tenga en cuenta la referencia cultural mediante los métodos estáticos <xref:System.Array> que toman un parámetro <xref:System.StringComparer?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#32)]  
  
 Las clases de colección como <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> y <xref:System.Collections.Generic.List%601?displayProperty=fullName> tienen constructores que toman un parámetro <xref:System.StringComparer?displayProperty=fullName> cuando el tipo de los elementos o las claves es `string`.  En general, debe usar estos constructores siempre que sea posible y especificar `Ordinal` u `OrdinalIgnoreCase`.  
  
## Vea también  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [Comparar cadenas](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)   
 [Globalizar y localizar aplicaciones](/visual-studio/ide/globalizing-and-localizing-applications)