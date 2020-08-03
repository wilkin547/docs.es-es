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
ms.openlocfilehash: b5d93efd278a53a4e6382f2321918e58ead55899
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865091"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="0c679-104">Procedimiento para enlazar un delegado mediante la reflexión</span><span class="sxs-lookup"><span data-stu-id="0c679-104">How to: Hook Up a Delegate Using Reflection</span></span>
<span data-ttu-id="0c679-105">Cuando se usa la reflexión para cargar y ejecutar ensamblados, no se pueden usar características del lenguaje como el operador `+=` de C# o la [instrucción AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md) de Visual Basic para enlazar eventos.</span><span class="sxs-lookup"><span data-stu-id="0c679-105">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="0c679-106">Los procedimientos siguientes muestran cómo enlazar un método existente a un evento obteniendo todos los tipos necesarios mediante reflexión y cómo crear un método dinámico utilizando la emisión de la reflexión y enlazarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-106">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c679-107">Para conocer otra manera de enlazar un delegado de control de eventos, vea el ejemplo de código del método <xref:System.Reflection.EventInfo.AddEventHandler%2A> de la clase <xref:System.Reflection.EventInfo>.</span><span class="sxs-lookup"><span data-stu-id="0c679-107">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="0c679-108">Para enlazar un delegado mediante la reflexión</span><span class="sxs-lookup"><span data-stu-id="0c679-108">To hook up a delegate using reflection</span></span>  
  
1. <span data-ttu-id="0c679-109">Cargue un ensamblado que contenga un tipo que provoque eventos.</span><span class="sxs-lookup"><span data-stu-id="0c679-109">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="0c679-110">Los ensamblados normalmente se cargan con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c679-110">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0c679-111">Para mantener la simplicidad de este ejemplo, se utiliza un formulario derivado del ensamblado actual, de manera que se utilice el método <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> para cargar el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="0c679-111">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. <span data-ttu-id="0c679-112">Obtenga un objeto <xref:System.Type> que represente el tipo y cree una instancia de dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="0c679-112">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="0c679-113">El método <xref:System.Activator.CreateInstance%28System.Type%29> se utiliza en el código siguiente porque el formulario tiene un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="0c679-113">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a parameterless constructor.</span></span> <span data-ttu-id="0c679-114">Hay varias otras sobrecargas del método <xref:System.Activator.CreateInstance%2A> que puede utilizar si el tipo que está creando no tiene un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="0c679-114">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a parameterless constructor.</span></span> <span data-ttu-id="0c679-115">La nueva instancia se almacena como tipo <xref:System.Object> para mantener la ficción de que no se sabe nada sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0c679-115">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="0c679-116">(La reflexión le permite obtener los tipos de un ensamblado sin conocer de antemano sus nombres.)</span><span class="sxs-lookup"><span data-stu-id="0c679-116">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. <span data-ttu-id="0c679-117">Obtenga un objeto <xref:System.Reflection.EventInfo> que represente el evento y utilice la propiedad <xref:System.Reflection.EventInfo.EventHandlerType%2A> para obtener el tipo de delegado utilizado para controlar el evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-117">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="0c679-118">En el código siguiente, se obtiene <xref:System.Reflection.EventInfo> para el evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="0c679-118">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. <span data-ttu-id="0c679-119">Obtenga un objeto <xref:System.Reflection.MethodInfo> que representa el método que controla el evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-119">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="0c679-120">Todo el código del programa de la sección Ejemplo, que se encuentra más adelante en este tema, contiene un método que coincide con la signatura del delegado <xref:System.EventHandler>, que controla el evento <xref:System.Windows.Forms.Control.Click>, pero también puede generar métodos dinámicos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c679-120">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="0c679-121">Para obtener detalles, vea el procedimiento de acompañamiento para generar un controlador de eventos en tiempo de ejecución usando un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="0c679-121">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. <span data-ttu-id="0c679-122">Cree una instancia del delegado utilizando el método <xref:System.Delegate.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c679-122">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="0c679-123">Este método es estático (`Shared` en Visual Basic), por lo que se debe proporcionar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="0c679-123">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="0c679-124">Se recomienda utilizar las sobrecargas de <xref:System.Delegate.CreateDelegate%2A> que toman <xref:System.Reflection.MethodInfo>.</span><span class="sxs-lookup"><span data-stu-id="0c679-124">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. <span data-ttu-id="0c679-125">Obtenga el método del descriptor de acceso `add` e invóquelo para enlazar el evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-125">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="0c679-126">Todos los eventos tienen un descriptor de acceso `add` y un descriptor de acceso `remove`, que son ocultados por la sintaxis de los lenguajes de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="0c679-126">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="0c679-127">Por ejemplo, C# usa el operador `+=` para enlazar eventos y Visual Basic usa la [instrucción AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0c679-127">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="0c679-128">El código siguiente obtiene el descriptor de acceso `add` del evento <xref:System.Windows.Forms.Control.Click> y lo invoca enlazado en tiempo de ejecución, pasando la instancia del delegado.</span><span class="sxs-lookup"><span data-stu-id="0c679-128">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="0c679-129">Los argumentos se deben pasar como una matriz.</span><span class="sxs-lookup"><span data-stu-id="0c679-129">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. <span data-ttu-id="0c679-130">Pruebe el evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-130">Test the event.</span></span> <span data-ttu-id="0c679-131">El código siguiente muestra el formulario definido en el ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="0c679-131">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="0c679-132">Al hacer clic en el formulario, se invoca el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0c679-132">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="0c679-133">Para generar un controlador de eventos en tiempo de ejecución utilizando un método dinámico</span><span class="sxs-lookup"><span data-stu-id="0c679-133">To generate an event handler at run time by using a dynamic method</span></span>  
  
1. <span data-ttu-id="0c679-134">utilizando métodos dinámicos ligeros y la emisión de reflexión se pueden generar métodos de controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c679-134">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="0c679-135">Para construir un controlador de eventos, es necesario conocer el tipo de valor devuelto y los tipos de parámetros del delegado.</span><span class="sxs-lookup"><span data-stu-id="0c679-135">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="0c679-136">Éstos se pueden obtener examinando el método `Invoke` del delegado.</span><span class="sxs-lookup"><span data-stu-id="0c679-136">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="0c679-137">El código siguiente utiliza los métodos `GetDelegateReturnType` y `GetDelegateParameterTypes` para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="0c679-137">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="0c679-138">El código para estos métodos se puede encontrar más adelante en este tema, en la sección Ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c679-138">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="0c679-139">No es necesario asignar nombre a <xref:System.Reflection.Emit.DynamicMethod>, por lo que se puede utilizar la cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0c679-139">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="0c679-140">En el código siguiente, el último argumento asocia el método dinámico con el tipo actual, dando al delegado acceso a todos los miembros públicos y privados de la clase `Example`.</span><span class="sxs-lookup"><span data-stu-id="0c679-140">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. <span data-ttu-id="0c679-141">Genere un cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="0c679-141">Generate a method body.</span></span> <span data-ttu-id="0c679-142">Este método carga una cadena, llama a la sobrecarga del método <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> que toma una cadena, saca el valor devuelto de la pila (porque el controlador no tiene tipo de valor devuelto) y vuelve.</span><span class="sxs-lookup"><span data-stu-id="0c679-142">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="0c679-143">Para más información sobre cómo emitir métodos dinámicos, vea [Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0c679-143">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. <span data-ttu-id="0c679-144">Finalice el método dinámico llamando a su método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c679-144">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="0c679-145">Utilice el descriptor de acceso `add` para agregar el delegado a la lista de invocación del evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-145">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. <span data-ttu-id="0c679-146">Pruebe el evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-146">Test the event.</span></span> <span data-ttu-id="0c679-147">El código siguiente carga el formulario definido en el ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="0c679-147">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="0c679-148">Al hacer clic en el formulario se invocan el controlador de eventos predefinido y el controlador de eventos emitido.</span><span class="sxs-lookup"><span data-stu-id="0c679-148">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="0c679-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c679-149">Example</span></span>  
 <span data-ttu-id="0c679-150">El siguiente ejemplo de código muestra cómo enlazar un método existente con un evento utilizando la reflexión y cómo utilizar la clase <xref:System.Reflection.Emit.DynamicMethod> para emitir un método en tiempo de ejecución y enlazarlo con un evento.</span><span class="sxs-lookup"><span data-stu-id="0c679-150">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c679-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c679-151">See also</span></span>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [<span data-ttu-id="0c679-152">Cómo: Definir y ejecutar métodos dinámicos</span><span class="sxs-lookup"><span data-stu-id="0c679-152">How to: Define and Execute Dynamic Methods</span></span>](how-to-define-and-execute-dynamic-methods.md)
- [<span data-ttu-id="0c679-153">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c679-153">Reflection</span></span>](reflection.md)
