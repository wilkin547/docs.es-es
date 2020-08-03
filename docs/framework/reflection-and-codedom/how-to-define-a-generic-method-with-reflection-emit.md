---
title: Procedimiento para definir un tipo genérico con emisión de reflexión
description: Defina un método genérico con emisión de reflexión. En un ejemplo se crea un método genérico con dos parámetros de tipo. En el segundo ejemplo se muestra cómo emitir el cuerpo del método.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic methods
- generics [.NET Framework], dynamic types
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
ms.openlocfilehash: 3b85fb480e5862daa3b2800f75392adbe92348f2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865143"
---
# <a name="how-to-define-a-generic-method-with-reflection-emit"></a>Procedimiento para definir un tipo genérico con emisión de reflexión

El primer procedimiento explica cómo crear un método genérico simple con dos parámetros de tipo y cómo aplicar restricciones de clase, restricciones de interfaz y restricciones especiales a los parámetros de tipo.

El segundo procedimiento muestra cómo emitir el cuerpo del método y cómo utilizar los parámetros de tipo del método genérico para crear instancias de tipos genéricos y llamar a sus métodos.

El tercero de los procedimientos explica cómo invocar el método genérico.

> [!IMPORTANT]
> Un método no es genérico sólo porque pertenece a un tipo genérico y utiliza los parámetros de tipo de ese tipo genérico. Un método sólo es genérico si tiene su propia lista de parámetros de tipo. Un método genérico puede aparecer en un tipo no genérico, como se puede ver en este ejemplo. Para obtener un ejemplo de un método no genérico en un tipo genérico, vea [Cómo: Definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-type-with-reflection-emit.md).

### <a name="to-define-a-generic-method"></a>Para definir un método genérico

1. Antes de comenzar, resulta de utilidad examinar cómo aparece el método genérico cuando se escribe utilizando un lenguaje de alto nivel. El código siguiente se incluye en el código de ejemplo de este tema, junto con el código para llamar al método genérico. El método tiene dos parámetros de tipo, `TInput` y `TOutput`, el segundo de los cuales debe ser de un tipo de referencia (`class`), tener un constructor sin parámetros (`new`) e implementar `ICollection(Of TInput)` (`ICollection<TInput>` en C#). Esta restricción de interfaz garantiza que el método <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType> se puede utilizar para agregar los elementos a la colección `TOutput` que crea el método. El método tiene un parámetro formal, `input`, que es una matriz de `TInput`. El método crea una colección de tipo `TOutput` y copia los elementos de `input` en la colección.

    [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
    [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]

2. Defina un ensamblado dinámico y un módulo dinámico para contener el tipo al que pertenece el método genérico. En este caso, el ensamblado sólo tiene un módulo, denominado `DemoMethodBuilder1`, y el nombre del módulo es el mismo que el nombre del ensamblado más una extensión. En este ejemplo, el ensamblado se guarda en el disco y se ejecuta, por lo que se especifica <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>. Puede usar [Ildasm.exe (Desensamblador de IL)](../tools/ildasm-exe-il-disassembler.md) para examinar DemoMethodBuilder1.dll y compararlo con el lenguaje intermedio de Microsoft (MSIL) para el método que se muestra en el paso 1.

    [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
    [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]

3. Defina el tipo al que pertenece la definición de método genérico. No es necesario que el tipo sea genérico. Una definición de método genérico puede pertenecer tanto a un tipo genérico como no genérico. En este ejemplo, el tipo es una clase, no es genérico y se denomina `DemoType`.

    [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
    [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]

4. Defina el método genérico. Si los tipos de los parámetros formales de un método genérico se especifican mediante los parámetros de tipo genérico del método genérico, utilice la sobrecarga del método <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29> para definir el método. Los parámetros de tipo genérico del método todavía no están definidos, por lo que no puede especificar los tipos de los parámetros formales del método en la llamada a <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A>. En este ejemplo, el método se denomina `Factory`. El método es público y `static` (`Shared` en Visual Basic).

    [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
    [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]

5. Defina los parámetros de tipo genérico de `DemoMethod` pasando una matriz de cadenas que contienen los nombres de los parámetros al método <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. Esto hace que el método sea un método genérico. El código siguiente hace que `Factory` sea un método genérico con parámetros de tipo `TInput` y `TOutput`. Para facilitar la lectura del código, se crean variables con estos nombres para contener los objetos <xref:System.Reflection.Emit.GenericTypeParameterBuilder> que representan los dos parámetros de tipo.

    [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
    [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]

6. También tiene la opción de agregar restricciones especiales a los parámetros de tipo. Las restricciones especiales se agregan utilizando el método <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A>. En este ejemplo, `TOutput` está restringido a ser un tipo de referencia y tener un constructor sin parámetros.

    [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
    [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]

7. También tiene la opción de agregar restricciones de clase y de interfaz a los parámetros de tipo. En este ejemplo, el parámetro de tipo `TOutput` está restringido a tipos que implementan la interfaz `ICollection(Of TInput)` (`ICollection<TInput>` en C#). Esto garantiza que el método <xref:System.Collections.Generic.ICollection%601.Add%2A> se puede utilizar para agregar elementos.

    [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
    [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]

8. Defina los parámetros formales del método utilizando el método <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A>. En este ejemplo, el método `Factory` tiene un parámetro, una matriz de `TInput`. Este tipo se crea llamando al método <xref:System.Type.MakeArrayType%2A> de <xref:System.Reflection.Emit.GenericTypeParameterBuilder> que representa `TInput`. El argumento de <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> es una matriz de objetos <xref:System.Type>.

    [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
    [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]

9. Defina el tipo de valor devuelto para el método utilizando el método <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A>. En este ejemplo se devuelve una instancia de `TOutput`.

    [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
    [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]

10. Emita el cuerpo del método utilizando <xref:System.Reflection.Emit.ILGenerator>. Para obtener detalles, vea el procedimiento que lo acompaña para emitir el cuerpo del método.

    > [!IMPORTANT]
    > Cuando emita llamadas a métodos de tipo genérico y los argumentos de dichos tipos son parámetros de tipo del método genérico, debe utilizar las sobrecargas de los métodos `static`<xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>, <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>, y <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> de la clase <xref:System.Reflection.Emit.TypeBuilder> para obtener formas construidas de los métodos. El procedimiento de acompañamiento para emitir el cuerpo del método muestra esta operación.

11. Finalice el tipo que contiene el método y guarde el ensamblado. El procedimiento de acompañamiento para invocar el método genérico muestra dos maneras de invocar el método completado.

    [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
    [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]

<a name="procedureSection1"></a>

### <a name="to-emit-the-method-body"></a>Para emitir el cuerpo del método

1. Obtenga un generador de código y declare variables y etiquetas locales. El método <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A> se utiliza para declarar las variables locales. El método `Factory` tiene cuatro variables locales: `retVal`, que va a albergar el nuevo objeto `TOutput` devuelto por el método; `ic`, que va a contener el parámetro `TOutput` cuando se convierta en `ICollection(Of TInput)` (`ICollection<TInput>` en C#); `input`, que va a contener la matriz de entrada de objetos `TInput`; e `index`, que va a recorrer la matriz en iteración. El método también tiene dos etiquetas, una para entrar en el bucle (`enterLoop`) y otra para ir al principio del bucle (`loopAgain`), definidas utilizando el método <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A>.

    Lo primero que hace el método es cargar su argumento utilizando el código de operación <xref:System.Reflection.Emit.OpCodes.Ldarg_0> y almacenándolo en la variable local `input` mediante el código de operación <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
    [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]

2. Emita el código para crear una instancia de `TOutput`, utilizando la sobrecarga de método genérico del método <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. Utilizar esta sobrecarga requiere que el tipo especificado tenga un constructor sin parámetros, que es la razón para agregar esa restricción a `TOutput`. Cree el método genérico construido pasando `TOutput` a <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. Después de emitir el código para llamar al método, emita el código para almacenarlo en la variable local `retVal` utilizando <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
    [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]

3. Emita el código para convertir el nuevo objeto `TOutput` a `ICollection(Of TInput)` y almacenarlo en la variable local `ic`.

    [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
    [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]

4. Obtenga la información <xref:System.Reflection.MethodInfo> que representa el método <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>. El método actúa en una interfaz `ICollection(Of TInput)` (`ICollection<TInput>` en C#), por lo que es necesario obtener el método `Add` específico de ese tipo construido. El método <xref:System.Type.GetMethod%2A> no se puede obtener para obtener esta <xref:System.Reflection.MethodInfo> directamente desde `icollOfTInput` porque no se admite <xref:System.Type.GetMethod%2A> en tipos que se hayan construido con un <xref:System.Reflection.Emit.GenericTypeParameterBuilder>. En su lugar, llame a <xref:System.Type.GetMethod%2A> de `icoll`, que contiene la definición de tipo genérico para la interfaz genérica <xref:System.Collections.Generic.ICollection%601>. A continuación, utilice el método <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>`static` para generar <xref:System.Reflection.MethodInfo> para el tipo construido. El código siguiente muestra cómo hacerlo.

    [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
    [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]

5. Emita el código para inicializar la variable `index`, cargando un entero 0 de 32 bits y almacenándolo en la variable. Emita el código para bifurcar a la etiqueta `enterLoop`. Esta etiqueta no está marcada todavía, porque se encuentra dentro del bucle. El código del bucle se emite en el siguiente paso.

    [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
    [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]

6. Emita el código para el bucle. El primer paso es marcar el principio del bucle, llamando a <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> con la etiqueta `loopAgain`. Las instrucciones de bifurcación que utilicen la etiqueta señalarán ahora a este punto del código. El paso siguiente es colocar en la pila el objeto `TOutput`, convertido a `ICollection(Of TInput)`. No se necesita inmediatamente, pero debe estar en posición para llamar al método `Add`. A continuación, se inserta la matriz de entrada en la pila y, después, en la matriz se inserta la variable `index` que contiene el índice actual. El código de operación <xref:System.Reflection.Emit.OpCodes.Ldelem> extrae de la pila el índice y la matriz e inserta en la pila el elemento de matriz indizado. Ahora la pila está lista para la llamada al método <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>, que extrae de la pila la colección y el nuevo elemento, y agrega el elemento a la colección.

    En el resto del código del bucle se incrementa el índice y se comprueba si el bucle ha finalizado: el índice y un entero de 32 bits se insertan en la pila y se suman, dejando la suma en la pila; la suma se almacena en `index`. Se invoca <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> para establecer este punto como punto de entrada del bucle. Se vuelve a cargar el índice. La matriz de entrada se inserta en la pila y se emite <xref:System.Reflection.Emit.OpCodes.Ldlen> para obtener su longitud. Ahora en la pila están el índice y la longitud, y se emite <xref:System.Reflection.Emit.OpCodes.Clt> para compararlos. Si el índice es menor que la longitud, <xref:System.Reflection.Emit.OpCodes.Brtrue_S> se vuelve a bifurcar hasta el principio del bucle.

    [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
    [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]

7. Emita el código para insertar el objeto `TOutput` en la pila y volver del método. Ambas variables locales, `retVal` e `ic`, contienen referencias al nuevo `TOutput`; `ic` sólo se utiliza para tener acceso al método <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>.

    [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
    [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]

<a name="procedureSection2"></a>

### <a name="to-invoke-the-generic-method"></a>Para invocar el método genérico

1. `Factory` es una definición de método genérico. Para invocarlo, debe asignar los tipos a sus parámetros de tipo genérico. Para ello, utilice el método <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. El código siguiente crea un método genérico construido, especifica <xref:System.String> para `TInput` y `List(Of String)` (`List<string>` en C#) para `TOutput`, y muestra una representación de cadena del método.

    [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
    [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]

2. Para invocar el método enlazado en tiempo de ejecución, utilice el método <xref:System.Reflection.MethodBase.Invoke%2A>. El código siguiente crea una matriz de <xref:System.Object>, que contiene como único elemento una matriz de cadenas, y lo pasa como la lista de argumentos para el método genérico. El primer parámetro de <xref:System.Reflection.MethodBase.Invoke%2A> es una referencia nula porque el método es `static`. El valor devuelto se convierte a `List(Of String)` y se muestra su primer elemento.

    [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
    [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]

3. Para invocar el método mediante un delegado, debe tener un delegado que coincida con la firma del método genérico construido. Una manera fácil de hacerlo es crear un delegado genérico. El código siguiente crea una instancia del delegado genérico `D` definido en el código de ejemplo utilizando la sobrecarga del método <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType> e invoca el delegado. El rendimiento de los delegados es mejor que el de las llamadas enlazadas en tiempo de ejecución.

    [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
    [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]

4. También se puede llamar al método emitido desde un programa que haga referencia al ensamblado guardado.

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente crea un tipo no genérico, `DemoType`, con un método genérico, `Factory`. Este método tiene dos parámetros de tipo genérico: `TInput` para especificar un tipo de entrada y `TOutput` para especificar un tipo de salida. El parámetro de tipo `TOutput` está restringido a implementar `ICollection<TInput>` (`ICollection(Of TInput)` en Visual Basic), ser un tipo de referencia y tener un constructor sin parámetros.

El método tiene un parámetro formal que es una matriz de `TInput`. El método devuelve una instancia de `TOutput` que contiene todos los elementos de la matriz de entrada. `TOutput` puede ser cualquier tipo de colección genérico que implemente la interfaz genérica <xref:System.Collections.Generic.ICollection%601>.

Cuando se ejecuta el código, el ensamblado dinámico se guarda como DemoGenericMethod1.dll y se puede examinar con [Ildasm.exe (Desensamblador de IL)](../tools/ildasm-exe-il-disassembler.md).

> [!NOTE]
> Una buena manera de aprender cómo emitir código es escribir un programa de Visual Basic, C# o Visual C++ que realice la tarea que está intentando emitir y utilizar el desensamblador para examinar el código MSIL producido por el compilador.

El ejemplo de código incluye código fuente que es equivalente al método emitido. El método emitido se invoca enlazado en tiempo de ejecución y también utilizando un delegado genérico declarado en el ejemplo de código.

[!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
[!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Emit.MethodBuilder>
- [Cómo: Definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-type-with-reflection-emit.md)
