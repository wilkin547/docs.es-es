---
title: Procedimiento para definir y ejecutar métodos dinámicos
description: Vea cómo definir y ejecutar métodos dinámicos en .NET. Vea ejemplos de un método dinámico simple y un método dinámico enlazado a una instancia de una clase.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
ms.openlocfilehash: 7c68be91deb59ea9439e81561f50b7cc40766a45
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865117"
---
# <a name="how-to-define-and-execute-dynamic-methods"></a>Procedimiento para definir y ejecutar métodos dinámicos
En los procedimientos siguientes se muestra cómo definir y ejecutar un método dinámico simple y un método dinámico enlazado a una instancia de una clase. Para obtener más información sobre los métodos dinámicos, vea la clase <xref:System.Reflection.Emit.DynamicMethod> y [Reflection Emit Dynamic Method Scenarios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100)) (Escenarios de métodos dinámicos de emisión de reflexión).  
  
### <a name="to-define-and-execute-a-dynamic-method"></a>Para definir y ejecutar un método dinámico  
  
1. Declare un tipo delegado para ejecutar el método. Considere la posibilidad de usar un delegado genérico para minimizar el número de tipos delegados que necesita declarar. El código siguiente declara dos tipos delegados que podrían usarse para el método `SquareIt`, y uno de ellos es genérico.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2. Cree una matriz que especifique los tipos de parámetro para el método dinámico. En este ejemplo, el único parámetro es `int` (`Integer` en Visual Basic), por lo que la matriz solo tiene un elemento.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3. Creará un control <xref:System.Reflection.Emit.DynamicMethod>. En este ejemplo, el método se denomina `SquareIt`.  
  
    > [!NOTE]
    > No es necesario asignar un nombre a los métodos dinámicos, y estos no se pueden invocar por su nombre. Se admite que varios métodos dinámicos tengan el mismo nombre, pero el nombre aparece en pilas de llamadas y puede ser útil para la depuración.  
  
     El tipo del valor devuelto se especifica como `long`. El método está asociado con el módulo que contiene la clase `Example`, que contiene el código de ejemplo. Se puede especificar cualquier módulo cargado. El método dinámico actúa como un método `static` de nivel de módulo (`Shared` en Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4. Emita el cuerpo del método. En este ejemplo, se usa un objeto <xref:System.Reflection.Emit.ILGenerator> para emitir el Lenguaje Intermedio de Microsoft (MSIL). Como alternativa, se puede usar un objeto <xref:System.Reflection.Emit.DynamicILInfo> junto con generadores de código no administrado para emitir el cuerpo del método para un <xref:System.Reflection.Emit.DynamicMethod>.  
  
     En este ejemplo, MSIL carga el argumento (que es `int`) en la pila, lo convierte en `long`, duplica `long` y multiplica los dos números. Esto deja el resultado al cuadrado en la pila, y lo único que tiene que hacer el método es devolverlo.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5. Llame al método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> para crear una instancia del delegado (declarado en el paso 1) que represente el método dinámico. La creación del delegado finaliza el método y todos los intentos posteriores de cambiar el método (por ejemplo, mediante la adición de MSIL) se omiten. El código siguiente crea el delegado y lo invoca mediante un delegado genérico.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### <a name="to-define-and-execute-a-dynamic-method-that-is-bound-to-an-object"></a>Para definir y ejecutar un método dinámico enlazado a un objeto  
  
1. Declare un tipo delegado para ejecutar el método. Considere la posibilidad de usar un delegado genérico para minimizar el número de tipos delegados que necesita declarar. El código siguiente declara un tipo delegado genérico que puede usarse para ejecutar cualquier método con un parámetro y un valor devuelto, o un método con dos parámetros y un valor devuelto si el delegado está enlazado a un objeto.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2. Cree una matriz que especifique los tipos de parámetro para el método dinámico. Si el delegado que representa el método va a enlazarse a un objeto, el primer parámetro debe coincidir con el tipo al que se enlaza el delegado. En este ejemplo, hay dos parámetros, de tipo `Example` y tipo `int` (`Integer` en Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3. Creará un control <xref:System.Reflection.Emit.DynamicMethod>. En este ejemplo el método no tiene nombre. El tipo del valor devuelto se especifica como `int` (`Integer` in Visual Basic). El método tiene acceso a los miembros privados y protegidos de la clase `Example`.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4. Emita el cuerpo del método. En este ejemplo, se usa un objeto <xref:System.Reflection.Emit.ILGenerator> para emitir el Lenguaje Intermedio de Microsoft (MSIL). Como alternativa, se puede usar un objeto <xref:System.Reflection.Emit.DynamicILInfo> junto con generadores de código no administrado para emitir el cuerpo del método para un <xref:System.Reflection.Emit.DynamicMethod>.  
  
     En este ejemplo, MSIL carga el primer argumento, que es una instancia de la clase `Example`, y lo usa para cargar el valor de un campo de instancia privada de tipo `int`. Se carga el segundo argumento y se multiplican los dos números. Si el resultado es mayor que `int`, el valor se trunca y se descartan los bits más significativos. El método devuelve un valor, con el valor devuelto en la pila.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5. Cree una instancia del delegado (declarado en el paso 1) que represente el método dinámico mediante una llamada a la sobrecarga del método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>. La creación del delegado finaliza el método y todos los intentos posteriores de cambiar el método (por ejemplo, mediante la adición de MSIL) se omiten.  
  
    > [!NOTE]
    > Puede llamar al método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> varias veces para crear delegados enlazados a otras instancias del tipo de destino.  
  
     El código siguiente enlaza el método a una nueva instancia de la clase `Example` cuyo campo de prueba privado está establecido en 42. Es decir, cada vez que se invoca el delegado, la instancia de `Example` se pasa al primer parámetro del método.  
  
     Se usa el delegado `OneParameter` porque el primer parámetro del método siempre recibe la instancia de `Example`. Cuando se invoca el delegado, solo es necesario el segundo parámetro.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra un método dinámico simple y un método dinámico enlazado a una instancia de una clase.  
  
 El método dinámico simple toma un argumento, un entero de 32 bits, y devuelve el cuadrado de 64 bits de ese entero. Se usa un delegado genérico para invocar el método.  
  
 El segundo método dinámico tiene dos parámetros, de tipo `Example` y tipo `int` (`Integer` en Visual Basic). Cuando se ha creado el método dinámico, se enlaza a una instancia de `Example` mediante un delegado genérico que tiene un argumento de tipo `int`. El delegado no tiene un argumento de tipo `Example` porque el primer parámetro del método siempre recibe la instancia enlazada de `Example`. Cuando se invoca el delegado, solo se proporciona el argumento `int`. Este método dinámico obtiene acceso a un campo privado de la clase `Example` y devuelve el producto del campo privado y el argumento `int`.  
  
 En el ejemplo de código se definen delegados que pueden usarse para ejecutar los métodos.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Emit.DynamicMethod>
- [Using Reflection Emit (Uso de la emisión de la reflexión)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Escenarios de métodos dinámicos de emisión de reflexión](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100))
