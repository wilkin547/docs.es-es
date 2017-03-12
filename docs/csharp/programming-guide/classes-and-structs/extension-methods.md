---
title: "M&#233;todos de extensi&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "métodos de extensión [C#]"
  - "métodos [C#], agregar a tipos existentes"
  - "métodos [C#], extensión"
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# M&#233;todos de extensi&#243;n (Gu&#237;a de programaci&#243;n de C#)
Los métodos de extensión permiten "agregar" métodos a los tipos existentes sin crear un nuevo tipo derivado, recompilar o modificar de otra manera el tipo original.  Los métodos de extensión son una clase especial de método estático, pero se les llama como si fueran métodos de instancia en el tipo extendido.  En el caso del código de cliente escrito en C\# y Visual Basic, no existe ninguna diferencia aparente entre llamar a un método de extensión y llamar a los métodos realmente definidos en un tipo.  
  
 Los métodos de extensión más comunes son los operadores de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] estándar, que agregan funcionalidad de consulta a los tipos <xref:System.Collections.IEnumerable?displayProperty=fullName> y <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> existentes.  Para usar los operadores de consulta estándar, inclúyalos primero en el ámbito con una directiva `using System.Linq`.  A partir de ese momento, cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601> parecerá tener métodos de instancia como <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>, etc.  Puede ver estos métodos adicionales en la finalización de instrucciones de IntelliSense al escribir "punto" después de una instancia de un tipo <xref:System.Collections.Generic.IEnumerable%601>, como <xref:System.Collections.Generic.List%601> o <xref:System.Array>.  
  
 En el ejemplo siguiente se muestra cómo llamar al método `OrderBy` de operador de consulta estándar en una matriz de enteros.  La expresión entre paréntesis es una expresión lambda.  Muchos operadores de consulta estándar toman expresiones lambda como parámetros, pero no es un requisito para los métodos de extensión.  Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 [!code-cs[csProgGuideExtensionMethods#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/extension-methods_1.cs)]  
  
 Los métodos de extensión se definen como métodos estáticos, pero se les llama usando la sintaxis de método de instancia.  El primer parámetro especifica en qué tipo funciona el método y va precedido del modificador [this](../../../csharp/language-reference/keywords/this.md).  Los métodos de extensión únicamente se encuentran dentro del ámbito cuando el espacio de nombres se importa explícitamente en el código fuente con una directiva `using`.  
  
 En el ejemplo siguiente se muestra un método de extensión definido para la clase <xref:System.String?displayProperty=fullName>.  Observe que se define dentro de una clase estática no anidada y no genérica:  
  
 [!code-cs[csProgGuideExtensionMethods#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/extension-methods_2.cs)]  
  
 El método de extensión `WordCount` se puede incluir en el ámbito con esta directiva `using`:  
  
```  
using ExtensionMethods;  
```  
  
 También se le puede llamar desde una aplicación con esta sintaxis:  
  
```  
string s = "Hello Extension Methods";  
int i = s.WordCount();  
```  
  
 En el código, el método de extensión se invoca con la sintaxis de método de instancia.  Sin embargo, el lenguaje intermedio \(IL\) generado por el compilador convierte el código en una llamada en el método estático.  Por lo tanto, el principio de encapsulación no se infringe realmente.  De hecho, los métodos de extensión no pueden tener acceso a las variables privadas en el tipo que extienden.  
  
 Para obtener más información, vea [Cómo: Implementar e invocar un método de extensión personalizado](../../../csharp/programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).  
  
 En general, probablemente se llamará a métodos de extensión con mucha más frecuencia de la que se implementarán métodos propios.  Dado que los métodos de extensión se llaman con la sintaxis de método de instancia, no se requieren conocimientos especiales para usarlos desde el código de cliente.  Para habilitar los métodos de extensión para un tipo determinado, basta con agregar una directiva `using` para el espacio de nombres en el que se definen los métodos.  Por ejemplo, para usar los operadores de consulta estándar, agregue esta directiva `using` al código:  
  
```  
using System.Linq;  
```  
  
 \(Puede que haya que agregar también una referencia a System.Core.dll\). Observará que los operadores de consulta estándar aparecen ahora en IntelliSense como métodos adicionales disponibles para la mayoría de los tipos <xref:System.Collections.Generic.IEnumerable%601>.  
  
> [!NOTE]
>  Aunque los operadores de consulta estándar no aparezcan en IntelliSense para <xref:System.String>, siguen estando disponibles.  
  
## Enlazar métodos de extensión en tiempo de compilación  
 Se pueden usar métodos de extensión para ampliar una clase o interfaz, pero no para invalidarlas.  Nunca se llamará a un método de extensión con el mismo nombre y signatura que un método de interfaz o clase.  En tiempo de compilación, los métodos de extensión siempre tienen menos prioridad que los métodos de instancia definidos en el propio tipo.  En otras palabras, si un tipo tiene un método denominado `Process(int i)` y hay un método de extensión con la misma signatura, el compilador siempre se enlazará al método de instancia.  Cuando el compilador encuentra una invocación de método, primero busca una coincidencia en los métodos de instancia del tipo.  Si no la hay, buscará cualquier método de extensión definido para el tipo y se enlazará al primer método de extensión que encuentre.  En el ejemplo siguiente se muestra cómo determina el compilador a qué método de extensión o de instancia enlazarse.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran las reglas que el compilador de C\# sigue para determinar si se va a enlazar una llamada a método a un método de instancia del tipo o a un método de extensión.  La clase estática `Extensions` contiene métodos de extensión definidos para cualquier tipo que implemente `IMyInterface`.  Las clases `A`, `B` y `C` implementan la interfaz.  
  
 Nunca se llama al método de extensión `MethodB`, porque su nombre y signatura coinciden exactamente con los métodos ya implementados por las clases.  
  
 Si el compilador no encuentra un método de instancia con una signatura coincidente, se enlazará a un método de extensión coincidente, si existe.  
  
 [!code-cs[csProgGuideExtensionMethods#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/extension-methods_3.cs)]  
  
## Instrucciones generales  
 En general, recomendamos que se implementen métodos de extensión con moderación y únicamente cuando sea necesario.  Siempre que sea posible, el código de cliente que debe extender un tipo existente debería hacerlo creando un nuevo tipo derivado del existente.  Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Al usar un método de extensión para ampliar un tipo cuyo código fuente no se puede cambiar, se corre el riesgo de que un cambio en la implementación del tipo interrumpa el método de extensión.  
  
 Si se implementan métodos de extensión para un tipo determinado, recuerde los puntos siguientes:  
  
-   Nunca se llamará a un método de extensión si tiene la misma signatura que un método definido en el tipo.  
  
-   Los métodos de extensión se incluyen en el ámbito en el nivel de espacio de nombres.  Por ejemplo, si se tienen varias clases estáticas que contienen métodos de extensión en un único espacio de nombres denominado `Extensions`, la directiva `using Extensions;` los incluirá a todos en el ámbito.  
  
 Para una biblioteca de clases ya implementada, no deben usarse métodos de extensión para evitar incrementar el número de versión de un ensamblado.  Si desea agregar una funcionalidad significativa a una biblioteca de la que es propietario del código fuente, deben seguirse las instrucciones de .NET Framework estándar para el control de versiones de ensamblado.  Para obtener más información, vea [Versiones de los ensamblados](../Topic/Assembly%20Versioning.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Ejemplos de programación en paralelo \(incluyen numerosos métodos de extensión de ejemplo\)](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Reglas de conversión para los parámetros de instancia y su impacto](http://go.microsoft.com/fwlink/?LinkId=112385)   
 [Interoperabilidad de los métodos de extensión entre lenguajes](http://go.microsoft.com/fwlink/?LinkId=112386)   
 [Métodos de extensión y delegados currificados](http://go.microsoft.com/fwlink/?LinkId=112387)   
 [Enlazar métodos de extensión y notificación de errores](http://go.microsoft.com/fwlink/?LinkId=112388)