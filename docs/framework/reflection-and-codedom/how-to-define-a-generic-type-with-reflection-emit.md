---
title: Procedimiento para definir un tipo genérico con emisión de reflexión
description: Vea cómo definir un tipo genérico con emisión de reflexión. Cree un tipo genérico con dos parámetros de tipo, aplique restricciones de clase, restricciones de interfaz y mucho más.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- generics [.NET Framework], dynamic types
- reflection emit, generic types
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
ms.openlocfilehash: bf308b07bf4b2a863b9825e7c8d9f412bdb6d1b8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559218"
---
# <a name="how-to-define-a-generic-type-with-reflection-emit"></a>Procedimiento para definir un tipo genérico con emisión de reflexión
En este tema se muestra cómo crear un tipo genérico simple con dos parámetros de tipo, cómo aplicar restricciones de clase, restricciones de interfaz y restricciones especiales a los parámetros de tipo, y cómo crear miembros que usen los parámetros de tipo de la clase como tipos de parámetro y tipos de valor devuelto.  
  
> [!IMPORTANT]
> Un método no es genérico sólo porque pertenece a un tipo genérico y utiliza los parámetros de tipo de ese tipo genérico. Un método sólo es genérico si tiene su propia lista de parámetros de tipo. La mayoría de los métodos de los tipos genéricos no son genéricos, como en este ejemplo. Para obtener un ejemplo de emisión de un método genérico, vea [Procedimiento para definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-method-with-reflection-emit.md).  
  
### <a name="to-define-a-generic-type"></a>Para definir un tipo genérico  
  
1. Defina un ensamblado dinámico denominado `GenericEmitExample1`. En este ejemplo, el ensamblado se ha ejecutado y guardado en el disco, por lo que se especifica <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2. Defina un módulo dinámico. Un ensamblado se compone de módulos ejecutables. En el caso de un ensamblado de un solo módulo, el nombre del módulo es el mismo que el nombre del ensamblado y el nombre del archivo es el nombre del módulo más una extensión.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3. Defina una clase. En este ejemplo, la clase se denomina `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4. Defina los parámetros de tipo genérico de `Sample` pasando una matriz de cadenas que contienen los nombres de los parámetros al método <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. Esto convierte a la clase en un tipo genérico. El valor devuelto es una matriz de objetos <xref:System.Reflection.Emit.GenericTypeParameterBuilder> que representan los parámetros de tipo y que se pueden usar en el código emitido.  
  
     En el código siguiente, `Sample` se convierte en un tipo genérico con parámetros de tipo `TFirst` y `TSecond`. Para que el código sea más fácil de leer, cada <xref:System.Reflection.Emit.GenericTypeParameterBuilder> se coloca en una variable con el mismo nombre que el parámetro de tipo.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5. Agregue restricciones especiales a los parámetros de tipo. En este ejemplo, el parámetro de tipo `TFirst` está restringido a tipos que tienen constructores sin parámetros y a tipos de referencia.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6. También tiene la opción de agregar restricciones de clase y de interfaz a los parámetros de tipo. En este ejemplo, el parámetro de tipo `TFirst` está restringido a tipos que derivan de la clase base representada por el objeto <xref:System.Type> incluido en la variable `baseType` y que implementan las interfaces cuyos tipos están incluidos en las variables `interfaceA` y `interfaceB`. Vea en el ejemplo de código la declaración y la asignación de estas variables.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7. Defina un campo. En este ejemplo, el tipo del campo es especificado por el parámetro de tipo `TFirst`. <xref:System.Reflection.Emit.GenericTypeParameterBuilder> deriva de <xref:System.Type>, por lo que puede usar parámetros de tipo genérico en cualquier lugar en que se pueda usar un tipo.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8. Defina un método que use los parámetros del tipo genérico. Tenga en cuenta que estos métodos no son genéricos a menos que tengan sus propias listas de parámetros de tipo. El código siguiente define un método `static` (`Shared` en Visual Basic) que toma una matriz de `TFirst` y devuelve un tipo `List<TFirst>` (`List(Of TFirst)` en Visual Basic) que contiene todos los elementos de la matriz. Para definir este método, es necesario crear el tipo `List<TFirst>`. Para ello, se llama a <xref:System.Type.MakeGenericType%2A> en la definición de tipo genérico, `List<T>`. (`T` se omite cuando se usa el operador `typeof` [`GetType` en Visual Basic] para obtener la definición de tipo genérico). El tipo de parámetro se crea con el método <xref:System.Type.MakeArrayType%2A>.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Emita el cuerpo del método. El cuerpo del método consta de tres códigos de operación que cargan la matriz de entrada en la pila, llaman al constructor `List<TFirst>` que toma `IEnumerable<TFirst>` (que hace todo el trabajo de colocar los elementos de entrada en la lista) y devuelven (dejando el nuevo objeto <xref:System.Collections.Generic.List%601> en la pila). La parte difícil a la hora de emitir este código es la obtención del constructor.  
  
     El método <xref:System.Type.GetConstructor%2A> no se admite en un <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, por lo que no es posible obtener el constructor de `List<TFirst>` directamente. En primer lugar, es necesario obtener el constructor de la definición de tipo genérico `List<T>` y luego llamar a un método que lo convierta en el constructor correspondiente de `List<TFirst>`.  
  
     El constructor usado para este ejemplo de código toma un tipo `IEnumerable<T>`. Pero tenga en cuenta que no es la definición de tipo genérico de la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>; en su lugar, debe sustituirse el parámetro de tipo `T` de `List<T>` por el parámetro de tipo `T` de `IEnumerable<T>`. (Esto parece confuso solo porque ambos tipos tienen parámetros de tipo con el nombre `T`. Por eso este ejemplo de código usa los nombres `TFirst` y `TSecond`). Para obtener el tipo del argumento del constructor, comience con la definición de tipo genérico `IEnumerable<T>` y llame a <xref:System.Type.MakeGenericType%2A> con el primer parámetro de tipo genérico de `List<T>`. La lista de argumentos del constructor se debe pasar como matriz, con un único argumento en este caso.  
  
    > [!NOTE]
    > La definición de tipo genérico se expresa como `IEnumerable<>` cuando se usa el operador `typeof` de C#, o como `IEnumerable(Of )` cuando se usa el operador `GetType` de Visual Basic.  
  
     Ahora es posible obtener el constructor de `List<T>` con una llamada a <xref:System.Type.GetConstructor%2A> en la definición de tipo genérico. Para convertir este constructor en el constructor correspondiente de `List<TFirst>`, pase `List<TFirst>` y el constructor de `List<T>` al método estático <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Cree el tipo y guarde el archivo.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Invoque al método. `ExampleMethod` no es genérico, pero el tipo al que pertenece sí lo es, así que para obtener un elemento <xref:System.Reflection.MethodInfo> que pueda invocarse es necesario crear un tipo construido de la definición de tipo para `Sample`. El tipo construido usa la clase `Example`, que satisface las restricciones de `TFirst` porque es un tipo de referencia y tiene un constructor sin parámetros predeterminado, y la clase `ExampleDerived`, que satisface las restricciones de `TSecond`. (El código de `ExampleDerived` puede encontrarse en la sección de código de ejemplo). Estos dos tipos se pasan a <xref:System.Type.MakeGenericType%2A> para crear el tipo construido. Luego se obtiene <xref:System.Reflection.MethodInfo> mediante el método <xref:System.Type.GetMethod%2A>.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. El código siguiente crea una matriz de objetos `Example`, coloca esa matriz en una matriz de tipo <xref:System.Object> que representa los argumentos del método que se va a invocar y los pasa al método <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>. El primer argumento del método <xref:System.Reflection.MethodBase.Invoke%2A> es una referencia nula porque el método es `static`.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define una clase denominada `Sample` junto con una clase base y dos interfaces. El programa define dos parámetros de tipo genérico para `Sample`, con lo que lo convierte en un tipo genérico. Los parámetros de tipo son lo único que convierte un tipo genérico. El programa lo indica al mostrar un mensaje de prueba antes y después de la definición de los parámetros de tipo.  
  
 El parámetro de tipo `TSecond` se usa para mostrar las restricciones de interfaz y de clase, mediante la clase base y las interfaces, y el parámetro de tipo `TFirst` se emplea para mostrar restricciones especiales.  
  
 El ejemplo de código define un campo y un método con los parámetros de tipo de la clase para el tipo de campo y para el parámetro y el tipo devuelto del método.  
  
 Una vez creada la clase `Sample`, se invoca al método.  
  
 El programa incluye un método que enumera información sobre un tipo genérico y un método que enumera las restricciones especiales de un parámetro de tipo. Estos métodos se usan para mostrar información sobre la clase finalizada `Sample`.  
  
 El programa guarda el módulo finalizado en el disco como `GenericEmitExample1.dll`, por lo que se puede abrir con [Ildasm.exe (Desensamblador de IL)](../tools/ildasm-exe-il-disassembler.md) y examinar el MSIL de la clase `Sample`.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Emit.GenericTypeParameterBuilder>
- [Using Reflection Emit (Uso de la emisión de la reflexión)](/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Reflection Emit Dynamic Assembly Scenarios (Escenarios de ensamblado dinámico de emisión de la reflexión)](/previous-versions/dotnet/netframework-4.0/tt9483fk(v=vs.100))
