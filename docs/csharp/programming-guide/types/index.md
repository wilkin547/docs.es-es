---
title: "Tipos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "tipos de valor [C#]"
  - "tipos de referencia [C#]"
  - "tipos [C#]"
  - "lenguaje C#, tipos de datos"
  - "sistema de tipos comunes [C#]"
  - "tipos de datos [C#]"
  - "lenguaje C#, tipos"
  - "tipado fuerte [C#]"
ms.assetid: f782d7cc-035e-4500-b1b1-36a9881130ad
caps.latest.revision: 53
caps.handback.revision: 53
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tipos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Tipos, variables y valores  
 C\# es un lenguaje fuertemente tipado.  Todas las variables y constantes tienen un tipo, al igual que toda expresión que da como resultado un valor.  Cada firma de método especifica un tipo para cada parámetro de entrada y para el valor devuelto.  La biblioteca de clases .NET Framework define un conjunto de tipos numéricos integrados y tipos más complejos que representan una amplia variedad de construcciones lógicas, como el sistema de archivos, conexiones de red, colecciones y matrices de objetos y fechas.  Un programa típico de C\# usa los tipos de la biblioteca de clases, así como tipos definidos por el usuario que modelan los conceptos específicos del dominio problemático del programa.  
  
 La información almacenada en un tipo puede incluir lo siguiente:  
  
-   El espacio de almacenamiento que requiere una variable del tipo.  
  
-   Los valores máximo y mínimo que puede representar.  
  
-   Los miembros \(métodos, campos, eventos, etc.\) que contiene.  
  
-   El tipo base del que hereda.  
  
-   La ubicación donde se asignará la memoria para las variables en tiempo de ejecución.  
  
-   Los tipos de operaciones permitidos.  
  
 El compilador utiliza información de tipos para asegurarse de que todas las operaciones que se realizan en el código cumplen la *seguridad de tipos*.  Por ejemplo, si declara una variable de tipo [int](../../../csharp/language-reference/keywords/int.md), el compilador permite utilizar la variable en operaciones de suma y resta.  Si intenta realizar esas mismas operaciones con una variable de tipo [bool](../../../csharp/language-reference/keywords/bool.md), el compilador genera un error, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideTypes#42](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_1.cs)]  
  
> [!NOTE]
>  Los desarrolladores de C y C\+\+ deben tener en cuenta que en C\# [bool](../../../csharp/language-reference/keywords/bool.md) no se puede convertir en [int](../../../csharp/language-reference/keywords/int.md).  
  
 El compilador incrusta la información de tipos en el archivo ejecutable en forma de metadatos.  Common Language Runtime \(CLR\) utiliza dichos metadatos en tiempo de ejecución para reforzar la garantía de la seguridad de tipos cuando asigna y reclama memoria.  
  
### Especificar los tipos en declaraciones de variables  
 Al declarar una variable o una constante en un programa, debe especificar su tipo o utilizar la palabra clave [var](../../../csharp/language-reference/keywords/var.md) para permitir que el compilador infiera el tipo.  En el ejemplo siguiente se muestran algunas declaraciones de variables que utilizan tipos numéricos integrados y tipos complejos definidos por el usuario:  
  
 [!code-cs[csProgGuideTypes#36](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_2.cs)]  
  
 Los tipos de los parámetros de método y de los valores devueltos se especifican en la firma del método.  La firma siguiente muestra un método que requiere [int](../../../csharp/language-reference/keywords/int.md) como argumento de entrada y devuelve una cadena:  
  
 [!code-cs[csProgGuideTypes#35](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_3.cs)]  
  
 Una vez declarada una variable, ésta no se puede volver a declarar con un nuevo tipo y tampoco se le puede asignar un valor que no sea compatible con su tipo declarado.  Por ejemplo, no puede declarar [int](../../../csharp/language-reference/keywords/int.md) y, a continuación, asignarle un valor booleano de [true](../../../csharp/language-reference/keywords/true-literal.md).  Sin embargo, los valores pueden convertirse en otros tipos, por ejemplo, cuando se asignan a variables nuevas o se pasan como argumentos de método.  Una *conversión de tipos* que no ocasiona una pérdida de datos la realiza automáticamente el compilador.  Una conversión que puede causar una pérdida de datos requiere una *conversión de tipos* en el código fuente.  
  
 Para obtener más información, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
## Tipos integrados  
 C\# proporciona un conjunto estándar de tipos numéricos integrados para representar enteros, valores de punto flotante, expresiones Boolean, caracteres de texto, valores decimales y otros tipos de datos.  También hay tipos `object` y `string` integrados.  Dichos tipos están disponibles para que los utilice en cualquier programa de C\#.  Para obtener más información sobre los tipos integrados, vea [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md).  
  
## Tipos personalizados  
 Las construcciones [struct](../../../csharp/language-reference/keywords/struct.md), [class](../../../csharp/language-reference/keywords/class.md), [interface](../../../csharp/language-reference/keywords/interface.md) y [enum](../../../csharp/language-reference/keywords/enum.md) se utilizan para crear sus propios tipos personalizados.  La biblioteca de clases de .NET Framework en sí es una colección de tipos personalizados proporcionada por Microsoft que puede utilizar en sus propias aplicaciones.  De forma predeterminada, los tipos usados con mayor frecuencia en la biblioteca de clases están disponibles en cualquier programa de C\#.  Otros solo están disponibles cuando se agrega explícitamente una referencia del proyecto al ensamblado en el que se definen.  Una vez que el compilador incluye una referencia al ensamblado, puede declarar variables \(y constantes\) de los tipos declarados en dicho ensamblado en el código fuente.  Para obtener más información, vea [Biblioteca de clases de .NET Framework](http://go.microsoft.com/fwlink/?LinkID=217856).  
  
## Sistema de tipos comunes  
 Es importante entender dos puntos fundamentales sobre el sistema de tipos en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]:  
  
-   Éste admite el principio de herencia.  Los tipos pueden derivarse de otros tipos denominados *tipos base*.  El tipo derivado hereda \(con algunas restricciones\) los métodos, las propiedades y otros miembros del tipo base.  A su vez, el tipo base puede derivarse de algún otro tipo; en este caso, el tipo derivado hereda los miembros de ambos tipos base en su jerarquía de herencia.  Todos los tipos, incluidos los tipos numéricos integrados como <xref:System.Int32?displayProperty=fullName> \(palabra clave de C\#: [int](../../../csharp/language-reference/keywords/int.md)\), se derivan en última instancia de un único tipo base, que es <xref:System.Object?displayProperty=fullName> \(palabra clave de C\#: [object](../../../csharp/language-reference/keywords/object.md)\).  Esta jerarquía de tipos unificados se denomina [Sistema de tipos comunes](../../../standard/base-types/common-type-system.md) \(CTS\).  Para obtener más información sobre la herencia en C\#, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
-   Cada uno de los tipos de CTS se define como un *tipo de valor* o un *tipo de referencia*.  Esto incluye todos los tipos personalizados de la biblioteca de clases .NET Framework y también los tipos propios definidos por el usuario.  Los tipos que define mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md) son tipos de valor; todos los tipos numéricos integrados son `structs`.  Los tipos que define mediante la palabra clave [class](../../../csharp/language-reference/keywords/class.md) son tipos de referencia.  Los tipos de referencia y los tipos de valor tienen distintas reglas de tiempo de compilación y un comportamiento diferente en tiempo de ejecución.  
  
 En la ilustración siguiente se muestra la relación entre los tipos de valor y los tipos de referencia en CTS.  
  
 ![Tipos de valor y tipos de referencia](../../../csharp/programming-guide/types/media/valuetypescts.png "ValueTypesCTS")  
Tipos de valor y tipos de referencia en CTS  
  
> [!NOTE]
>  Puede ver que todos los tipos utilizados con más frecuencia se organizan en el espacio de nombres <xref:System>.  Sin embargo, el espacio de nombres en el que se incluye un tipo no tiene ninguna relación con el hecho de que sea un tipo de valor o un tipo de referencia.  
  
### Tipos de valor  
 Los tipos de valor se derivan de <xref:System.ValueType?displayProperty=fullName>, que a su vez se deriva de <xref:System.Object?displayProperty=fullName>.  Los tipos que se derivan de <xref:System.ValueType?displayProperty=fullName> tienen un comportamiento especial en CLR.  Las variables de tipo de valor contienen directamente sus valores, lo que significa que la memoria se asigna insertándola en cualquier contexto en el que se declare la variable.  En las variables de tipo de valor no se produce una asignación de memoria independiente en el montón ni una sobrecarga de recolección de elementos no utilizados.  
  
 Hay dos categorías de tipos de valor: [struct](../../../csharp/language-reference/keywords/struct.md) y [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Los tipos numéricos integrados son structs con propiedades y métodos a los que puede tener acceso:  
  
```c#  
// Static method on type Byte.  
byte b = Byte.MaxValue;  
```  
  
 Sin embargo, la declaración y asignación de valores a dichos tipos se realizan como si fueran tipos simples no agregados:  
  
```c#  
byte num = 0xA;  
int i = 5;  
char c = 'Z';  
```  
  
 Los tipos de valor son *sealed*, lo que significa, por ejemplo, que no puede derivar un tipo de <xref:System.Int32?displayProperty=fullName> y que no puede definir un struct para que herede de cualquier clase o struct definidos por el usuario, ya que un struct solo puede heredar de <xref:System.ValueType?displayProperty=fullName>.  Sin embargo, un struct puede implementar una o varias interfaces.  Puede convertir un tipo de struct en un tipo de interfaz; esto hace que una operación de *conversión boxing* encapsule el struct en un objeto de tipo de referencia del montón administrado.  Las operaciones de conversión boxing tienen lugar al pasar un tipo de valor a un método que toma un elemento <xref:System.Object?displayProperty=fullName> como parámetro de entrada.  Para obtener más información, vea [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
 La palabra clave [struct](../../../csharp/language-reference/keywords/struct.md) se usa para crear sus propios tipos de valor personalizados.  Normalmente, un struct se utiliza como contenedor de un pequeño conjunto de variables relacionadas, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/index_4.cs)]  
  
 Para obtener más información sobre los structs, vea [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).  Para obtener más información sobre los tipos de valor en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], vea [Sistema de tipos comunes](../../../standard/base-types/common-type-system.md).  
  
 La otra categoría de tipos de valor es [enum](../../../csharp/language-reference/keywords/enum.md).  Una enumeración define un conjunto de constantes integrales con nombre.  Por ejemplo, la enumeración <xref:System.IO.FileMode?displayProperty=fullName> de la biblioteca de clases .NET Framework contiene un conjunto de enteros constantes con nombre que especifican cómo debe abrirse un archivo.  Se define como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideTypes#44](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_5.cs)]  
  
 La constante `System.IO.FileMode.Create` tiene un valor 2.  Sin embargo, el nombre es mucho más significativo para los humanos que leen el código fuente y, por esa razón, es mejor utilizar enumeraciones en lugar de números de literal constante.  Para obtener más información, vea <xref:System.IO.FileMode?displayProperty=fullName>.  
  
 Todas las enumeraciones heredan de <xref:System.Enum?displayProperty=fullName>, que a su vez hereda de <xref:System.ValueType?displayProperty=fullName>.  Todas las reglas aplicables a los structs también se aplican a las enumeraciones.  Para obtener más información sobre las enumeraciones, vea [Tipos de enumeración](../../../csharp/programming-guide/enumeration-types.md).  
  
### Tipos de referencia  
 Un tipo que se define como [clase](../../../csharp/language-reference/keywords/class.md), [delegado](../../../csharp/language-reference/keywords/delegate.md), matriz o [interfaz](../../../csharp/language-reference/keywords/interface.md) es un *tipo de referencia*.  Al declarar una variable de un tipo de referencia en tiempo de ejecución, la variable contiene el valor [null](../../../csharp/language-reference/keywords/null.md) hasta que se crea explícitamente una instancia del objeto mediante el operador [new](../../../csharp/language-reference/keywords/new.md) o se le asigna un objeto creado en otro lugar mediante `new, as shown in the following example:`.  
  
```c#  
MyClass mc = new MyClass();  
MyClass mc2 = mc;  
```  
  
 Una interfaz debe inicializarse junto con un objeto de clase que la implementa.  Si `MyClass` implementa `IMyInterface`, cree una instancia de `IMyInterface` como se muestra en el ejemplo siguiente:  
  
```c#  
IMyInterface iface = new MyClass();  
```  
  
 Cuando se crea el objeto, se asigna la memoria en el montón administrado y la variable solo contiene una referencia a la ubicación del objeto.  Los tipos del montón administrado producen sobrecarga cuando se asignan y cuando los reclama la funcionalidad de administración de memoria automática de CLR, conocida como *recolección de elementos no utilizados*.  Sin embargo, la recolección de elementos no utilizados también está muy optimizada y no crea problemas de rendimiento en la mayoría de los casos.  Para obtener más información acerca de la recolección de elementos no utilizados, vea [Administración de memoria automática](../Topic/Automatic%20Memory%20Management.md).  
  
 Todas las matrices son tipos de referencia, incluso si sus elementos son tipos de valor.  Las matrices se derivan implícitamente de la clase <xref:System.Array?displayProperty=fullName>, pero se declaran y utilizan con la sintaxis simplificada proporcionada por C\#, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideTypes#45](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_6.cs)]  
  
 Los tipos de referencia admiten la herencia.  Al crear una clase, se puede heredar de cualquier otra interfaz o clase que no esté definida como [sealed](../../../csharp/language-reference/keywords/sealed.md); además, otras clases pueden heredar de la clase que ha creado e invalidar sus métodos virtuales.  Para obtener más información sobre cómo crear sus propias clases, vea [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md).  Para obtener más información acerca de la herencia y los métodos virtuales, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
## Tipos de valores literales  
 En C\#, los valores literales reciben un tipo del compilador.  Para especificar el tipo de un literal numérico, anexe una letra al final del número.  Por ejemplo, para especificar que el valor 4.56 debe tratarse como tipo flotante, anexe una "f" o "F" después del número: `4.56f`.  Si no se anexa ninguna letra, el compilador inferirá un tipo para el literal.  Para obtener más información sobre los tipos que pueden especificarse con sufijos de letras, vea las páginas de referencia de los tipos individuales en [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md).  
  
 Puesto que los literales tienen tipos y todos los tipos se derivan en última instancia de <xref:System.Object?displayProperty=fullName>, puede escribir y compilar código como el que se muestra a continuación:  
  
 [!code-cs[csProgGuideTypes#37](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_7.cs)]  
  
## Tipos genéricos  
 Un tipo se puede declarar con uno o varios *parámetros de tipo* que actúan como marcador de posición del tipo real \(el *tipo concreto*\) que proporcionará el código cliente al crear una instancia del tipo.  Estos tipos se denominan *tipos genéricos*.  Por ejemplo, el tipo de .NET Framework <xref:System.Collections.Generic.List%601?displayProperty=fullName> tiene un parámetro de tipo al que, por convención, se le asigna el nombre *T*.  Cuando se crea una instancia del tipo, se especifica el tipo de los objetos que incluirá la lista, por ejemplo, cadena:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 El uso de un parámetro de tipo hace que sea posible reutilizar la misma clase para incluir cualquier tipo de elemento, sin tener que convertir cada elemento en [object](../../../csharp/language-reference/keywords/object.md).  Las clases de colección genéricas se denominan *colecciones fuertemente tipadas* porque el compilador conoce el tipo específico de los elementos de la colección y puede producir un error en tiempo de compilación si, por ejemplo, se intenta agregar un entero al objeto `strings` en el ejemplo anterior.  Para obtener más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).  
  
## Tipos implícitos, tipos anónimos y tipos que aceptan valores NULL  
 Como ya se ha mencionado anteriormente, puede indicar el tipo implícito de una variable local \(pero no de los miembros de clase\) mediante la palabra clave [var](../../../csharp/language-reference/keywords/var.md).  La variable sigue recibiendo un tipo en tiempo de compilación, pero el tipo lo proporciona el compilador.  Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 En algunos casos, es conveniente crear un tipo con nombre para conjuntos sencillos de valores relacionados que no están destinados a almacenarse o pasarse fuera de los límites del método.  Para este fin, puede crear *tipos anónimos*.  Para obtener más información, consulte [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 Los tipos de valor normales no pueden tener el valor [null](../../../csharp/language-reference/keywords/null.md).  Sin embargo, puede crear tipos de valor que acepten valores NULL si anexa `?` después del tipo.  Por ejemplo, `int?` es un tipo `int` que también puede tener el valor [null](../../../csharp/language-reference/keywords/null.md).  En CTS, los tipos que aceptan valores NULL son instancias del tipo de struct genérico <xref:System.Nullable%601?displayProperty=fullName>.  Dichos tipos resultan especialmente útiles al pasar datos desde y hacia bases de datos en las que los valores numéricos pueden ser null.  Para obtener más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
## Secciones relacionadas  
 Para obtener más información, vea los temas siguientes:  
  
-   [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
  
-   [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)  
  
-   [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
  
-   [Genéricos](../../../csharp/programming-guide/generics/index.md)  
  
-   [Variables y expresiones](http://go.microsoft.com/fwlink/?LinkId=221228) en [Iniciando Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Conversión de tipos de datos XML](../Topic/Conversion%20of%20XML%20Data%20Types.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)