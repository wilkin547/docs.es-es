---
title: "How to: Define a Generic Type with Reflection Emit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "generics [.NET Framework], reflection emit"
  - "generics [.NET Framework], dynamic types"
  - "reflection emit, generic types"
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Define a Generic Type with Reflection Emit
Este tema explica cómo crear un tipo genérico simple con dos parámetros de tipo, cómo aplicar restricciones de clases, restricciones de interfaz y restricciones especiales a los parámetros de tipo, y cómo crear miembros que utilicen los parámetros de tipo de la clase como tipos de parámetro y tipos devueltos.  
  
> [!IMPORTANT]
>  Un método no es genérico sólo porque pertenece a un tipo genérico y utiliza los parámetros de tipo de ese tipo genérico.  Un método sólo es genérico si tiene su propia lista de parámetros de tipo.  La mayoría de los métodos de tipos genéricos no son genéricos, como en este ejemplo.  Para obtener un ejemplo de emisión de un método genérico, vea [How to: Define a Generic Method with Reflection Emit](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-method-with-reflection-emit.md).  
  
### Para definir un tipo genérico  
  
1.  Defina un ensamblado dinámico denominado `GenericEmitExample1`.  En este ejemplo, se ejecuta el ensamblado y se guarda en el disco, por lo que se especifica <xref:System.Reflection.Emit.AssemblyBuilderAccess?displayProperty=fullName>.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2.  Defina un módulo dinámico.  Un ensamblado se compone de módulos ejecutables.  Para un ensamblado de un único módulo, el nombre de módulo es el mismo que el del nombre de ensamblado y el nombre de archivo es el nombre del módulo más una extensión.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3.  Defina una clase.  En este ejemplo, la clase se denomina `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4.  Defina los parámetros de tipo genérico de `Sample` pasando una matriz de cadenas que contienen los nombres de los parámetros al método <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=fullName>.  De esta forma la clase se vuelve de tipo genérico.  El valor devuelto es una matriz de objetos <xref:System.Reflection.Emit.GenericTypeParameterBuilder> que representan los parámetros de tipo, que se pueden utilizar en el código emitido.  
  
     En el código siguiente, `Sample` se vuelve de tipo genérico con parámetros de tipo `TFirst` y `TSecond`.  Para facilitar la lectura del código, cada constructor <xref:System.Reflection.Emit.GenericTypeParameterBuilder> se coloca en una variable con el mismo nombre que el del parámetro de tipo.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5.  Agregue restricciones especiales a los parámetros de tipo.  En este ejemplo, el parámetro de tipo `TFirst` está restringido a tipos que tienen constructores sin parámetros y a tipos de referencia.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6.  También tiene la opción de agregar restricciones de clase y de interfaz a los parámetros de tipo.  En este ejemplo, el parámetro de tipo `TFirst` está restringido a los tipos derivados de la clase base representada por el objeto <xref:System.Type> contenido en la variable `baseType`, y que implementan las interfaces cuyos tipos están contenidos en las variables `interfaceA` e `interfaceB`.  Vea el ejemplo de código para la declaración y la asignación de estas variables.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7.  Defina un campo.  En este ejemplo, el tipo del campo se especifica mediante el parámetro de tipo `TFirst`.  <xref:System.Reflection.Emit.GenericTypeParameterBuilder> se deriva de <xref:System.Type>, para permitir el uso de parámetros de tipo genérico en cualquier lugar donde se pueda utilizar un tipo.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8.  Defina un método que utilice los parámetros de tipo del tipo genérico.  Observe que tales métodos no son genéricos a menos que tengan sus propias listas de parámetros de tipo.  El código siguiente define un método `static` \(`Shared` en Visual Basic\) que toma una matriz de `TFirst` y devuelve una `List<TFirst>` \(`List(Of TFirst)` en Visual Basic\) que contiene todos los elementos de la matriz.  Para definir este método, es necesario crear el tipo `List<TFirst>` llamando a <xref:System.Type.MakeGenericType%2A> en la definición de tipo genérico, `List<T>`. \(Se omite `T` cuando se utiliza el operador `typeof` \(`GetType` en Visual Basic\) para obtener la definición de tipo genérico.\) El tipo de parámetro se crea utilizando el método <xref:System.Type.MakeArrayType%2A>.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Emita el cuerpo del método.  El cuerpo del método consta de tres códigos de operación que cargan la matriz de entrada en la pila, llaman al constructor `List<TFirst>` que toma `IEnumerable<TFirst>` \(que realiza el trabajo de poner en la lista los elementos de entrada\), y vuelven \(dejando en la pila el nuevo objeto <xref:System.Collections.Generic.List%601>\).  La parte difícil de emitir este código es la de obtener el constructor.  
  
     El método <xref:System.Type.GetConstructor%2A> no se admite en un <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, por lo que no es posible de obtener directamente el constructor de `List<TFirst>`.  En primer lugar, es necesario obtener el constructor de la definición de tipo genérico `List<T>` y luego llamar a un método que lo convierta en el correspondiente constructor de `List<TFirst>`.  
  
     El constructor utilizado para este código toma una `IEnumerable<T>`.  Observe, sin embargo, que ésta no es la definición de tipo genérico de la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, sino que el parámetro de tipo `T` de `List<T>` debe sustituirse para el parámetro de tipo `T` de `IEnumerable<T>`. \(Esto puede parecer confuso sólo porque ambos tipos tienen parámetros de tipo denominados `T`.  Por eso en este ejemplo de código se utilizan los nombres `TFirst` y `TSecond`.\) Para obtener el tipo del argumento del constructor, comience con la definición de tipo genérico `IEnumerable<T>` y llame a <xref:System.Type.MakeGenericType%2A> con el primer parámetro de tipo genérico de `List<T>`.  La lista de argumentos de constructores se debe pasar como una matriz, con un único argumento en este caso.  
  
    > [!NOTE]
    >  La definición de tipo genérico se expresa como `IEnumerable<>` cuando se utiliza el operador `typeof` de C\# o `IEnumerable(Of )` cuando se usa el operador `GetType` de Visual Basic.  
  
     Ahora es posible obtener el constructor de `List<T>` llamando a <xref:System.Type.GetConstructor%2A> en la definición de tipo genérico.  Para convertir este constructor en el constructor correspondiente de `List<TFirst>`, pase `List<TFirst>` y el constructor desde `List<T>` al método <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=fullName> estático.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Cree el tipo y guarde el archivo.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Invoque el método.  `ExampleMethod` no es genérico, pero el tipo al que pertenece sí es genérico; por tanto, para obtener una <xref:System.Reflection.MethodInfo> que se pueda invocar es necesario crear un tipo construido a partir de la definición de tipo de `Sample`.  El tipo construido utiliza la clase `Example`, que satisface las restricciones de `TFirst` porque es un tipo de referencia y tiene un constructor predeterminado sin parámetros, y la clase `ExampleDerived` que satisface las restricciones de `TSecond`. \(El código para `ExampleDerived` se puede encontrar en la sección de código de ejemplo.\) Estos dos tipos se pasan a <xref:System.Type.MakeGenericType%2A> para crear el tipo construido.  <xref:System.Reflection.MethodInfo> se obtiene entonces utilizando el método <xref:System.Type.GetMethod%2A>.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. El código siguiente crea una matriz de objetos `Example`, coloca esa matriz en una matriz del tipo <xref:System.Object> que representa los argumentos del método que se va a invocar y los pasa al método [Invoke\(Object, Object\<xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>.  El primer argumento del método <xref:System.Reflection.MethodBase.Invoke%2A> es una referencia nula porque el método es `static`.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## Ejemplo  
 El ejemplo de código siguiente define una clase denominada `Sample`, junto con una clase base y dos interfaces.  El programa define dos parámetros de tipo genérico para `Sample`, convirtiéndolo en un tipo genérico.  Los parámetros de tipo son lo único que hace que un tipo sea genérico.  El programa lo indica mostrando un mensaje de prueba antes y después de la definición de los parámetros de tipo.  
  
 El parámetro de tipo `TSecond` se utiliza para explicar las restricciones de clase e interfaz, usando la clase y las interfaces base y, por último, el parámetro de tipo `TFirst` se emplea para ilustrar las restricciones especiales.  
  
 El ejemplo de código define un campo y un método que utiliza los parámetros de tipo de la clase para el tipo de campo y para el parámetro y el tipo de valor devuelto del método.  
  
 Después de haberse creado la clase `Sample`, se invoca el método.  
  
 El programa incluye un método que muestra información sobre un tipo genérico y un método que muestra las restricciones especiales en un parámetro de tipo.  Estos métodos se utilizan para mostrar información sobre la clase `Sample` terminada.  
  
 El programa guarda en disco el módulo terminado como `GenericEmitExample1.dll` para que pueda abrirlo con el [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) y examinar el código MSIL de la clase `Sample`.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## Compilar el código  
  
-   El código contiene las instrucciones `using` de C\# \(`Imports` en Visual Basic\) necesarias para la compilación.  
  
-   No se requiere ninguna referencia de ensamblado adicional.  
  
-   Compile el código de la línea de comandos mediante csc.exe, vbc.exe, o cl.exe.  Para compilar el código en Visual Studio, póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>   
 [Utilizar la emisión de la reflexión](http://msdn.microsoft.com/es-es/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Escenarios de ensamblado dinámico de emisión de la reflexión](http://msdn.microsoft.com/es-es/e1cc6750-e20f-473b-bb4e-f43bc66aecce)