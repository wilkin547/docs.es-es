---
title: Procedimiento para enlazar un delegado mediante la reflexión
description: Vea cómo enlazar un delegado mediante la reflexión en .NET. Conecte un método existente a un evento mediante la obtención de los tipos necesarios por medio de la reflexión.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
ms.openlocfilehash: 9a92afd1c2aeadeb0cf7bc1e626b5bd1fb3cecea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263430"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a>Procedimiento para enlazar un delegado mediante la reflexión

Cuando se usa la reflexión para cargar y ejecutar ensamblados, no se pueden usar características del lenguaje como el operador `+=` de C# o la [instrucción AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md) de Visual Basic para enlazar eventos. Los procedimientos siguientes muestran cómo enlazar un método existente a un evento obteniendo todos los tipos necesarios mediante reflexión y cómo crear un método dinámico utilizando la emisión de la reflexión y enlazarlo a un evento.  
  
> [!NOTE]
> Para conocer otra manera de enlazar un delegado de control de eventos, vea el ejemplo de código del método <xref:System.Reflection.EventInfo.AddEventHandler%2A> de la clase <xref:System.Reflection.EventInfo>.  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a>Para enlazar un delegado mediante la reflexión  
  
1. Cargue un ensamblado que contenga un tipo que provoque eventos. Los ensamblados normalmente se cargan con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>. Para mantener la simplicidad de este ejemplo, se utiliza un formulario derivado del ensamblado actual, de manera que se utilice el método <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> para cargar el ensamblado actual.  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. Obtenga un objeto <xref:System.Type> que represente el tipo y cree una instancia de dicho tipo. El método <xref:System.Activator.CreateInstance%28System.Type%29> se utiliza en el código siguiente porque el formulario tiene un constructor sin parámetros. Hay varias otras sobrecargas del método <xref:System.Activator.CreateInstance%2A> que puede utilizar si el tipo que está creando no tiene un constructor sin parámetros. La nueva instancia se almacena como tipo <xref:System.Object> para mantener la ficción de que no se sabe nada sobre el ensamblado. (La reflexión le permite obtener los tipos de un ensamblado sin conocer de antemano sus nombres.)  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. Obtenga un objeto <xref:System.Reflection.EventInfo> que represente el evento y utilice la propiedad <xref:System.Reflection.EventInfo.EventHandlerType%2A> para obtener el tipo de delegado utilizado para controlar el evento. En el código siguiente, se obtiene <xref:System.Reflection.EventInfo> para el evento <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. Obtenga un objeto <xref:System.Reflection.MethodInfo> que representa el método que controla el evento. Todo el código del programa de la sección Ejemplo, que se encuentra más adelante en este tema, contiene un método que coincide con la signatura del delegado <xref:System.EventHandler>, que controla el evento <xref:System.Windows.Forms.Control.Click>, pero también puede generar métodos dinámicos en tiempo de ejecución. Para obtener detalles, vea el procedimiento de acompañamiento para generar un controlador de eventos en tiempo de ejecución usando un método dinámico.  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. Cree una instancia del delegado utilizando el método <xref:System.Delegate.CreateDelegate%2A>. Este método es estático (`Shared` en Visual Basic), por lo que se debe proporcionar el tipo de delegado. Se recomienda utilizar las sobrecargas de <xref:System.Delegate.CreateDelegate%2A> que toman <xref:System.Reflection.MethodInfo>.  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. Obtenga el método del descriptor de acceso `add` e invóquelo para enlazar el evento. Todos los eventos tienen un descriptor de acceso `add` y un descriptor de acceso `remove`, que son ocultados por la sintaxis de los lenguajes de alto nivel. Por ejemplo, C# usa el operador `+=` para enlazar eventos y Visual Basic usa la [instrucción AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md). El código siguiente obtiene el descriptor de acceso `add` del evento <xref:System.Windows.Forms.Control.Click> y lo invoca enlazado en tiempo de ejecución, pasando la instancia del delegado. Los argumentos se deben pasar como una matriz.  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. Pruebe el evento. El código siguiente muestra el formulario definido en el ejemplo de código. Al hacer clic en el formulario, se invoca el controlador de eventos.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>

### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a>Para generar un controlador de eventos en tiempo de ejecución utilizando un método dinámico  
  
1. utilizando métodos dinámicos ligeros y la emisión de reflexión se pueden generar métodos de controlador de eventos en tiempo de ejecución. Para construir un controlador de eventos, es necesario conocer el tipo de valor devuelto y los tipos de parámetros del delegado. Éstos se pueden obtener examinando el método `Invoke` del delegado. El código siguiente utiliza los métodos `GetDelegateReturnType` y `GetDelegateParameterTypes` para obtener esta información. El código para estos métodos se puede encontrar más adelante en este tema, en la sección Ejemplo.  
  
     No es necesario asignar nombre a <xref:System.Reflection.Emit.DynamicMethod>, por lo que se puede utilizar la cadena vacía. En el código siguiente, el último argumento asocia el método dinámico con el tipo actual, dando al delegado acceso a todos los miembros públicos y privados de la clase `Example`.  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. Genere un cuerpo del método. Este método carga una cadena, llama a la sobrecarga del método <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> que toma una cadena, saca el valor devuelto de la pila (porque el controlador no tiene tipo de valor devuelto) y vuelve. Para más información sobre cómo emitir métodos dinámicos, vea [Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md).  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. Finalice el método dinámico llamando a su método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>. Utilice el descriptor de acceso `add` para agregar el delegado a la lista de invocación del evento.  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. Pruebe el evento. El código siguiente carga el formulario definido en el ejemplo de código. Al hacer clic en el formulario se invocan el controlador de eventos predefinido y el controlador de eventos emitido.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo de código muestra cómo enlazar un método existente con un evento utilizando la reflexión y cómo utilizar la clase <xref:System.Reflection.Emit.DynamicMethod> para emitir un método en tiempo de ejecución y enlazarlo con un evento.  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md)
- [Reflexión](reflection.md)
