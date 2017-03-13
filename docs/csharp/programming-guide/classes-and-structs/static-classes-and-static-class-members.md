---
title: "Clases est&#225;ticas y sus miembros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, clases estáticas"
  - "lenguaje C#, miembros estáticos"
  - "miembros de clases estáticas [C#]"
  - "clases estáticas [C#]"
  - "miembros estáticos [C#]"
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 49
---
# Clases est&#225;ticas y sus miembros (Gu&#237;a de programaci&#243;n de C#)
Una clase [estática](../../../csharp/language-reference/keywords/static.md) es básicamente igual que una clase no estática, pero existe una diferencia: no se pueden crear instancias de una clase estática.  En otras palabras, no puede utilizar la palabra clave [new](../../../csharp/language-reference/keywords/new.md) para crear una variable del tipo clase.  Dado que no hay ninguna variable de instancia, el acceso a los miembros de una clase estática se realiza mediante el propio nombre de clase.  Por ejemplo, si cuenta con una clase estática que se denomina `UtilityClass` e incluye un método público denominado `MethodA`, la llamada al método se realiza tal como se muestra en el ejemplo siguiente:  
  
```c#  
UtilityClass.MethodA();  
```  
  
 Una clase estática se puede utilizar como un contenedor adecuado para los conjuntos de métodos que solo funcionan en parámetros de entrada y no tienen que obtener ni establecer campos internos de instancia.  Por ejemplo, en la biblioteca de clases .NET Framework, la clase estática <xref:System.Math?displayProperty=fullName> contiene varios métodos que realizan operaciones matemáticas, sin ningún requisito para almacenar o recuperar datos únicos de una instancia determinada de la clase <xref:System.Math>.  Es decir, los miembros de la clase se aplican especificando el nombre de la clase y del método, como se muestra en el ejemplo siguiente.  
  
```  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
  
```  
  
 Como sucede con todos los tipos de clase, Common Language Runtime \(CLR\) de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] carga la información de tipo de una clase estática cuando se carga el programa que hace referencia a la clase. El programa no puede especificar exactamente cuándo se carga la clase.  Sin embargo, se garantiza que se ha cargado, que sus campos se han inicializado y que se ha llamado a su constructor estático antes de que se haga referencia a la clase por primera vez en el programa.  Solo se llama una vez a un constructor estático y una clase estática permanece en memoria durante el período de duración del dominio de aplicación donde reside el programa.  
  
> [!NOTE]
>  Para crear una clase no estática que permita crear solo una instancia de sí misma, vea [Implementing Singleton in C\#](http://go.microsoft.com/fwlink/?LinkID=100567).  
  
 En la siguiente lista se proporcionan las características principales de una clase estática:  
  
-   Solo contiene miembros estáticos.  
  
-   No se pueden crear instancias de ella.  
  
-   Es de tipo sealed.  
  
-   No puede contener [constructores de instancia](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Crear una clase estática es, por consiguiente, básicamente igual que crear una clase que solo contiene miembros estáticos y un constructor privado.  Un constructor privado evita que se creen instancias de la clase.  La ventaja de utilizar una clase estática es que el compilador puede comprobar que no se agregue accidentalmente ningún miembro de instancia.  El compilador garantizará que no se puedan crear instancias de esta clase.  
  
 Las clases estáticas son de tipo sealed y, por consiguiente, no pueden heredarse.  No pueden heredar de cualquier clase, excepto <xref:System.Object>.  Las clases estáticas no pueden contener un constructor de instancia; sin embargo, pueden contener un constructor estático.  Las clases no estáticas también deben definir un constructor estático si contienen miembros estáticos que requieren una inicialización no trivial.  Para obtener más información, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## Ejemplo  
 Este es un ejemplo de clase estática que contiene dos métodos que convierten la temperatura de grados Celsius a Fahrenheit y viceversa:  
  
 [!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## Miembros estáticos  
 Una clase no estática puede contener métodos, campos, propiedades o eventos estáticos.  El miembro estático es invocable en una clase incluso si no se ha creado ninguna instancia de la clase.  El nombre de clase, y no el nombre de instancia, es el que tiene acceso al miembro estático.  Solo existe una copia de un miembro estático, independientemente del número de instancias que se creen de la clase.  Los métodos y propiedades estáticos no pueden tener acceso a los campos y eventos no estáticos de su tipo contenedor y no pueden tener acceso a una variable de instancia de ningún objeto a menos que se pase explícitamente en un parámetro de método.  
  
 Es más habitual declarar una clase no estática con algunos miembros estáticos que declarar toda una clase como estática.  Dos usos comunes de los campos estáticos son mantener un recuento del número de objetos de los que se han creado instancias y almacenar un valor que se debe compartir entre todas las instancias.  
  
 Los métodos estáticos se pueden sobrecargar pero no invalidar, porque pertenecen a la clase y no a una instancia de la clase.  
  
 Aunque un campo no se puede declarar como `static const`, un campo [const](../../../csharp/language-reference/keywords/const.md) es esencialmente estático en su comportamiento.  Pertenece al tipo, no a las instancias del tipo.  Por tanto, se puede tener acceso a los campos de constante mediante la misma notación `ClassName.MemberName` que se utiliza para los campos estáticos.  No se requiere ninguna instancia de objeto.  
  
 C\# no admite las variables local estáticas \(variables que se declaran en el ámbito del método\).  
  
 Los miembros estáticos de la clase se declaran mediante la incorporación de la palabra clave `static` antes del tipo de valor devuelto del miembro, tal como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 Los miembros estáticos se inicializan antes de obtener acceso al miembro estático por primera vez y antes de llamar al constructor estático, si éste existe.  Para tener acceso a un miembro estático de la clase, utilice el nombre de la clase en lugar de un nombre de variable para especificar la ubicación del miembro, tal como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 Si la clase contiene campos estáticos, proporcione un constructor estático que los inicialice cuando se cargue la clase.  
  
 Una llamada a un método estático genera una instrucción de llamada en el lenguaje intermedio de Microsoft \(MSIL\), mientras que una llamada a un método de instancia genera una instrucción `callvirt`, que también comprueba las referencias de objeto nulas.  Sin embargo, la mayoría de las veces la diferencia de rendimiento entre ambas no es significativa.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [clase](../../../csharp/language-reference/keywords/class.md)   
 [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)   
 [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)