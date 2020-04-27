---
title: Cargar y utilizar tipos dinámicamente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- late binding, about late binding
- early binding
- dynamically loading and using types
- implicit late binding
- reflection, dynamically using types
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
ms.openlocfilehash: 940f334ec6a42c4d8da461d634051ff979b8f98d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130259"
---
# <a name="dynamically-loading-and-using-types"></a>Cargar y utilizar tipos dinámicamente
La reflexión facilita la infraestructura que utilizan los compiladores de lenguaje para implementar el enlace en tiempo de ejecución implícito. El enlace es el proceso de buscar la declaración (es decir, la implementación) que corresponde a un tipo especificado de manera exclusiva. Cuando este proceso se produce en tiempo de ejecución, en lugar de en tiempo de compilación, se denomina enlace en tiempo de ejecución. Visual Basic le permite usar el enlace en tiempo de ejecución implícito en el código; el compilador de Visual Basic llama a un método auxiliar que usa la reflexión para obtener el tipo de objeto. Los argumentos pasados al método del asistente hacen que se invoque el método adecuado en tiempo de ejecución. Estos argumentos son la instancia (un objeto) en la que se invoca el método, el nombre del método invocado (una cadena) y los argumentos pasados al método invocado (una matriz de objetos).  
  
 En el ejemplo siguiente, el compilador de Visual Basic usa implícitamente la reflexión para llamar a un método en un objeto cuyo tipo se desconoce en tiempo de compilación. Una clase **HelloWorld** tiene un método **PrintHello** que imprime "Hello World" de forma concatenada con texto que se pasa al método **PrintHello**. El método **PrintHello** llamado en este ejemplo es en realidad <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>; el código de Visual Basic permite invocar el método **PrintHello** como si se conociera el tipo del objeto (helloObj) en tiempo de compilación (enlace anticipado), y no en tiempo de ejecución (enlace en tiempo de ejecución).  
  
```vb
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## <a name="custom-binding"></a>Enlace personalizado  
 Además de usarla implícitamente los compiladores para el enlace en tiempo de ejecución, la reflexión puede usarse explícitamente en el código para realizar el enlace en tiempo de ejecución.  
  
 [Common Language Runtime](../../standard/clr.md) admite varios lenguajes de programación, y las reglas de enlace de estos lenguajes son diferentes. En el caso del enlace anticipado, los generadores de código pueden controlar completamente este enlace. Pero en el caso del enlace en tiempo de ejecución mediante reflexión, es necesario controlarlo mediante un enlace personalizado. La clase <xref:System.Reflection.Binder> proporciona un control personalizado de la selección e invocación de miembros.  
  
 Mediante el enlace personalizado, puede cargar un ensamblado en tiempo de ejecución, obtener información sobre los tipos del ensamblado, especificar el tipo que quiera y, después, invocar métodos u obtener acceso a campos o propiedades de dicho tipo. Esta técnica es útil si no conoce el tipo de un objeto en tiempo de compilación, como cuando el tipo de objeto depende de la entrada del usuario.  
  
 En el ejemplo siguiente se muestra un enlazador simple personalizado que no proporciona conversión de tipos de argumento. El ejemplo principal va precedido del código de `Simple_Type.dll`. Asegúrese de compilar `Simple_Type.dll` y, después, incluir una referencia a él en el proyecto en tiempo de compilación.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### <a name="invokemember-and-createinstance"></a>InvokeMember y CreateInstance  
 Use <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType> para invocar un miembro de un tipo. Los métodos **CreateInstance** de diversas clases, como <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.CreateInstance%2A?displayProperty=nameWithType>, son formas especializadas de **InvokeMember** que crean nuevas instancias del tipo especificado. La clase **Binder** se usa para la resolución de sobrecarga y la conversión de argumentos en estos métodos.  
  
 En el ejemplo siguiente se muestran las tres posibles combinaciones de conversión de argumentos (conversión de tipos) y selección de miembros. En el caso 1, no se necesita ni conversión de argumentos ni selección de miembros. En el caso 2, solo se necesita la selección de miembros. En el caso 3, solo se necesita la conversión de argumentos.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Se necesita la resolución de sobrecarga cuando hay más de un miembro con el mismo nombre. Los métodos <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=nameWithType> y <xref:System.Reflection.Binder.BindToField%2A?displayProperty=nameWithType> se usan para resolver el enlace en un solo miembro. **Binder.BindToMethod** también proporciona resolución de propiedades mediante los descriptores de acceso de propiedades **get** y **set**.  
  
 **BindToMethod** devuelve el <xref:System.Reflection.MethodBase> que se va a invocar o una referencia nula (**Nothing** en Visual Basic) si la invocación no es posible. No es necesario que el valor devuelto de **MethodBase** sea uno de los contenidos en el parámetro *match*, aunque esto es lo habitual.  
  
 Cuando hay argumentos ByRef, el llamador podría querer recuperarlos. Por lo tanto, **Binder** permite que un cliente asigne la matriz de argumentos de nuevo a su forma original si **BindToMethod** ha manipulado la matriz de argumentos. Para ello, debe garantizarse al llamador que el orden de los argumentos no se ha modificado. Cuando los argumentos se pasan por nombre, **Binder** reordena la matriz de argumentos, y esto es lo que ve el llamador. Para obtener más información, vea <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=nameWithType>.  
  
 El conjunto de miembros disponibles está integrado por los miembros definidos en el tipo o en cualquier tipo base. Si se especifica <xref:System.Reflection.BindingFlags>, se devolverán en el conjunto miembros de cualquier tipo de accesibilidad. Si no se especifica **BindingFlags.NonPublic**, el enlazador deberá imponer reglas de accesibilidad. Cuando especifique la marca de enlace **Public** o **NonPublic**, también debe especificar la marca de enlace **Instance** o **Static**. En caso contrario, no se devolverá ningún miembro.  
  
 Si solo hay un miembro con el nombre especificado, no es necesaria la devolución de la llamada y el enlace se realiza en dicho método. En el caso 1 del ejemplo de código se ilustra este punto: solo hay disponible un método **PrintBob** y, por tanto, no es necesaria la devolución de la llamada.  
  
 Si hay más de un miembro en el conjunto disponible, todos estos métodos se pasan a **BindToMethod**, que selecciona el método apropiado y lo devuelve. En el caso 2 del ejemplo de código, hay dos métodos denominados **PrintValue**. Mediante una llamada a **BindToMethod**, se selecciona el método apropiado.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> realiza la conversión de argumentos (conversión de tipos), que convierte los argumentos reales al tipo de los argumentos formales del método seleccionado. Se llama a **ChangeType** para cada argumento incluso si los tipos coinciden exactamente.  
  
 En el caso 3 del ejemplo de código, se pasa un argumento real de tipo **String** con un valor de "5.5" a un método con un argumento formal de tipo **Double**. Para que la invocación se realice correctamente, el valor de cadena "5.5" se debe convertir a un valor doble. **ChangeType** realiza esta conversión.  
  
 **ChangeType** solo realiza [conversiones de ampliación](../../standard/base-types/type-conversion.md) o sin pérdida de información, como se muestra en la tabla siguiente.  
  
|Tipo de origen|Tipo de destino|  
|-----------------|-----------------|  
|Cualquier tipo|Su tipo base|  
|Cualquier tipo|La interfaz que implementa|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Doble|  
|Tipo sin referencia|Tipo de referencia|  
  
 La clase <xref:System.Type> tiene métodos **Get** que usan parámetros de tipo **Binder** para resolver las referencias a un miembro concreto. <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType>, <xref:System.Type.GetMethod%2A?displayProperty=nameWithType> y <xref:System.Type.GetProperty%2A?displayProperty=nameWithType> buscan un miembro determinado del tipo actual, para lo que proporcionan información de firma de ese miembro. Se vuelve a llamar a <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=nameWithType> y <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=nameWithType> para seleccionar la información de firma especificada de los métodos apropiados.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- [Ver información tipos](viewing-type-information.md)
- [Conversión de tipos en .NET Framework](../../standard/base-types/type-conversion.md)
