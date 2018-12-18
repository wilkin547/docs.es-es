---
title: 'Clases y métodos parciales: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 222a47989537f09fd78c4a3b17fa8c1a5478d73f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243470"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a>Clases y métodos parciales (Guía de programación de C#)
Es posible dividir la definición de una [clase](../../../csharp/language-reference/keywords/class.md), un [struct](../../../csharp/language-reference/keywords/struct.md), una [interfaz](../../../csharp/language-reference/keywords/interface.md) o un método en dos o más archivos de código fuente. Cada archivo de código fuente contiene una sección de la definición de tipo o método, y todos los elementos se combinan cuando se compila la aplicación.  
  
## <a name="partial-classes"></a>Clases parciales  
 Es recomendable dividir una definición de clase en varias situaciones:  
  
-   Cuando se trabaja con proyectos grandes, el hecho de repartir una clase entre archivos independientes permite que varios programadores trabajen en ella al mismo tiempo.  
  
-   Cuando se trabaja con código fuente generado automáticamente, se puede agregar código a la clase sin tener que volver a crear el archivo de código fuente. Visual Studio usa este enfoque al crear formularios Windows Forms, código de contenedor de servicio Web, etc. Puede crear código que use estas clases sin necesidad de modificar el archivo creado por Visual Studio.  
  
-   Para dividir una definición de clase, use el modificador de palabra clave [partial](../../../csharp/language-reference/keywords/partial-type.md), como se muestra aquí:  
  
 [!code-csharp[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]  
  
 La palabra clave `partial` indica que se pueden definir en el espacio de nombres otros elementos de la clase, la estructura o la interfaz. Todos los elementos deben usar la palabra clave `partial`. Todos los elementos deben estar disponibles en tiempo de compilación para formar el tipo final. Todos los elementos deben tener la misma accesibilidad, como `public`, `private`, etc.  
  
 Si algún elemento se declara abstracto, todo el tipo se considera abstracto. Si algún elemento se declara sellado, todo el tipo se considera sellado. Si algún elemento declara un tipo base, todo el tipo hereda esa clase.  
  
 Todos los elementos que especifiquen una clase base deben coincidir, pero los elementos que omitan una clase base heredan igualmente el tipo base. Los elementos pueden especificar diferentes interfaces base, y el tipo final implementa todas las interfaces enumeradas por todas las declaraciones parciales. Todas las clases, structs o miembros de interfaz declarados en una definición parcial están disponibles para todos los demás elementos. El tipo final es la combinación de todos los elementos en tiempo de compilación.  
  
> [!NOTE]
>  El modificador `partial` no está disponible en declaraciones de delegado o enumeración.  
  
 En el ejemplo siguiente se muestra que los tipos anidados pueden ser parciales, incluso si el tipo en el que están anidados no es parcial.  
  
 [!code-csharp[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]  
  
 En tiempo de compilación, se combinan los atributos de definiciones de tipo parcial. Por ejemplo, consideremos las siguientes declaraciones:  
  
 [!code-csharp[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]  
  
 Son equivalentes a las declaraciones siguientes:  
  
 [!code-csharp[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]  
  
 A continuación se indican los elementos que se combinan de todas las definiciones de tipo parcial:  
  
-   comentarios XML  
  
-   interfaces  
  
-   atributos de parámetro de tipo genérico  
  
-   class (atributos)  
  
-   miembros  
  
 Por ejemplo, consideremos las siguientes declaraciones:  
  
 [!code-csharp[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]  
  
 Son equivalentes a las declaraciones siguientes:  
  
 [!code-csharp[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]  
  
### <a name="restrictions"></a>Restricciones  
 Debe seguir varias reglas al trabajar con definiciones de clase parcial:  
  
-   Todas las definiciones de tipo parcial que van a formar parte del mismo tipo deben modificarse con `partial`. Por ejemplo, las declaraciones de clase siguientes generan un error:  
  
     [!code-csharp[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]  
  
-   El modificador `partial` solo puede aparecer inmediatamente antes de las palabras clave `class`, `struct` o `interface`.  
  
-   Se permiten tipos parciales anidados en definiciones de tipo parcial, como se muestra en el ejemplo siguiente:  
  
     [!code-csharp[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]  
  
-   Todas las definiciones de tipo parcial que van a formar parte del mismo tipo deben definirse en el mismo ensamblado y en el mismo módulo (archivo .exe o .dll). Las definiciones parciales no pueden abarcar varios módulos.  
  
-   El nombre de clase y los parámetros de tipo genérico deben coincidir en todas las definiciones de tipo parcial. Los tipos genéricos pueden ser parciales. Cada declaración parcial debe usar los mismos nombres de parámetro en el mismo orden.  
  
-   Las siguientes palabras clave son opcionales en una definición de tipo parcial, pero si están presentes la definición, no pueden entrar en conflicto con las palabras clave especificadas en otra definición parcial para el mismo tipo:  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   clase base  
  
    -   modificador [new](../../../csharp/language-reference/keywords/new.md) (elementos anidados)  
  
    -   restricciones genéricas  
  
         Para obtener más información, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="example-1"></a>Ejemplo 1  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente, los campos y el constructor de la clase, `CoOrds`, se declaran en una definición de clase parcial y el miembro `PrintCoOrds` se declara en otra definición de clase parcial.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]  
  
## <a name="example-2"></a>Ejemplo 2  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra que también se pueden desarrollar structs e interfaces parciales.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]  
  
## <a name="partial-methods"></a>Métodos Partial  
 Una clase o struct parcial puede contener un método parcial. Un elemento de la clase contiene la firma del método. Se puede definir una implementación opcional en el mismo elemento o en otro. Si no se proporciona la implementación, el método y todas las llamadas al método se quitan en tiempo de compilación.  
  
 Los métodos parciales permiten que el implementador de un elemento de una clase defina un método, similar a un evento. El implementador del otro elemento de la clase puede decidir si quiere implementar el método o no. Si el método no se implementa, el compilador quita la firma del método y todas las llamadas al método. Las llamadas al método, incluidos los resultados que se producirían por la evaluación de los argumentos de las llamadas, no tienen efecto en tiempo de ejecución. Por lo tanto, el código de la clase parcial puede usar libremente un método parcial, incluso si no se proporciona la implementación. No se producirá ningún error en tiempo de compilación o en tiempo de ejecución si se llama al método pero no se implementa.  
  
 Los métodos parciales son especialmente útiles para personalizar el código generado. Permiten reservar un nombre y firma de método de modo que el código generado pueda llamar al método, pero el desarrollador decide si se implementa el método. De manera muy similar a como hacen las clases parciales, los métodos parciales permiten que el código creado por un generador de código y el código creado por un desarrollador humano funcionen juntos sin costos en tiempo de ejecución.  
  
 Una declaración de método parcial consta de dos elementos: la definición y la implementación. Pueden encontrarse en elementos independientes de una clase parcial o en el mismo elemento. Si no hay ninguna declaración de implementación, el compilador optimiza tanto la declaración de definición como todas las llamadas al método.  
  
```csharp  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Las declaraciones de método parcial deben comenzar con la palabra clave contextual [partial](../../../csharp/language-reference/keywords/partial-type.md) y el método debe devolver [void](../../../csharp/language-reference/keywords/void.md).  
  
-   Los métodos parciales pueden tener parámetros [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../../csharp/language-reference/keywords/ref.md), pero no parámetros [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).  
  
-   Los métodos parciales son implícitamente [private](../../../csharp/language-reference/keywords/private.md) y, por tanto, no pueden ser [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Los métodos parciales no pueden ser [extern](../../../csharp/language-reference/keywords/extern.md), ya que la presencia del cuerpo determina si son de definición o de implementación.  
  
-   Los métodos parciales pueden tener modificadores [static](../../../csharp/language-reference/keywords/static.md) y [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
-   Los métodos parciales pueden ser genéricos. Las restricciones se colocan en la declaración de método parcial de definición y opcionalmente pueden repetirse en el de implementación. Los nombres del parámetro y del parámetro de tipo no tienen que ser iguales en la declaración de implementación y en la declaración de definición.  
  
-   Puede crear un [delegado](../../../csharp/language-reference/keywords/delegate.md) para un método parcial que se ha definido e implementado, pero no para un método parcial que solo se ha definido.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Tipos parciales](~/_csharplang/spec/classes.md#partial-types) de la [Especificación del lenguaje C#](../../language-reference/language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)  
- [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)  
- [Interfaces](../../../csharp/programming-guide/interfaces/index.md)  
- [partial (Tipos)](../../../csharp/language-reference/keywords/partial-type.md)
