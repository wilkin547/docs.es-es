---
title: 'Cómo: Simular eventos del mouse y del teclado en el código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 9fac74aacf6b902a25438151db247a1a4aee1f4c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802484"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="84d88-102">Cómo: Simular eventos del mouse y del teclado en el código</span><span class="sxs-lookup"><span data-stu-id="84d88-102">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="84d88-103">Windows Forms ofrece varias opciones para simular la entrada de mouse y de teclado mediante programación.</span><span class="sxs-lookup"><span data-stu-id="84d88-103">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="84d88-104">En este tema se ofrece una introducción a estas opciones.</span><span class="sxs-lookup"><span data-stu-id="84d88-104">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="84d88-105">Simular la entrada de mouse</span><span class="sxs-lookup"><span data-stu-id="84d88-105">Simulating Mouse Input</span></span>

<span data-ttu-id="84d88-106">La mejor forma de simular eventos del mouse es llamar al método `On`*EventName* que genera el evento del mouse que quiere simular.</span><span class="sxs-lookup"><span data-stu-id="84d88-106">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="84d88-107">Normalmente, esta opción solo es posible dentro de controles y formularios personalizados, porque los métodos que generan eventos están protegidos y no se puede acceder a ellos fuera del control o formulario.</span><span class="sxs-lookup"><span data-stu-id="84d88-107">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="84d88-108">Por ejemplo, los siguientes pasos muestran cómo simular el clic con el botón secundario del mouse en el código.</span><span class="sxs-lookup"><span data-stu-id="84d88-108">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="84d88-109">Para hacer clic con el botón secundario del mouse mediante programación</span><span class="sxs-lookup"><span data-stu-id="84d88-109">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="84d88-110">Cree un <xref:System.Windows.Forms.MouseEventArgs> cuya propiedad <xref:System.Windows.Forms.MouseEventArgs.Button%2A> esté establecida en el valor <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="84d88-110">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="84d88-111">Llame al método <xref:System.Windows.Forms.Control.OnMouseClick%2A> con este <xref:System.Windows.Forms.MouseEventArgs> como argumento.</span><span class="sxs-lookup"><span data-stu-id="84d88-111">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="84d88-112">Para más información sobre controles personalizados, vea [Desarrollar controles de Windows Forms en tiempo de diseño](./controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="84d88-112">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="84d88-113">Hay otras maneras de simular la entrada de mouse.</span><span class="sxs-lookup"><span data-stu-id="84d88-113">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="84d88-114">Por ejemplo, puede establecer mediante programación una propiedad de control que representa un estado que normalmente se establece mediante la entrada de mouse (como la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> del control <xref:System.Windows.Forms.CheckBox> ), o puede llamar directamente al delegado que está asociado al evento que quiere simular.</span><span class="sxs-lookup"><span data-stu-id="84d88-114">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="84d88-115">Simular la entrada de teclado</span><span class="sxs-lookup"><span data-stu-id="84d88-115">Simulating Keyboard Input</span></span>

<span data-ttu-id="84d88-116">Aunque puede simular la entrada del teclado con las estrategias descritas anteriormente para la entrada de mouse, Windows Forms también proporciona la clase <xref:System.Windows.Forms.SendKeys> para enviar pulsaciones de tecla a la aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="84d88-116">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="84d88-117">Si su aplicación está pensada para su uso internacional con distintos teclados, <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> puede producir resultados imprevisibles y debe evitarse.</span><span class="sxs-lookup"><span data-stu-id="84d88-117">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="84d88-118">La clase <xref:System.Windows.Forms.SendKeys> se ha actualizado para .NET Framework 3.0 para que se pueda usar en aplicaciones que se ejecutan en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="84d88-118">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="84d88-119">La seguridad mejorada de Windows Vista (conocida como Control de cuentas de usuario o UAC) impide que la implementación anterior funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="84d88-119">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="84d88-120">La clase <xref:System.Windows.Forms.SendKeys> es susceptible de tener problemas de temporización que algunos desarrolladores han tenido que solucionar.</span><span class="sxs-lookup"><span data-stu-id="84d88-120">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="84d88-121">La implementación actualizada sigue siendo susceptible de tener problemas de temporización, pero es ligeramente más rápida y puede requerir cambios en las soluciones alternativas.</span><span class="sxs-lookup"><span data-stu-id="84d88-121">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="84d88-122">La clase <xref:System.Windows.Forms.SendKeys> intenta usar primero la implementación anterior y, si se produce un error, usa la nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="84d88-122">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="84d88-123">Como resultado, la clase <xref:System.Windows.Forms.SendKeys> puede comportarse de manera diferente en los distintos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="84d88-123">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="84d88-124">Además, cuando la clase <xref:System.Windows.Forms.SendKeys> usa la nueva implementación, el método <xref:System.Windows.Forms.SendKeys.SendWait%2A> no esperará a que se procesen los mensajes cuando se envían a otro proceso.</span><span class="sxs-lookup"><span data-stu-id="84d88-124">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="84d88-125">Si la aplicación depende de un comportamiento coherente independientemente del sistema operativo, puede forzar que la clase <xref:System.Windows.Forms.SendKeys> use la nueva implementación agregando la siguiente opción de configuración de la aplicación al archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="84d88-125">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="84d88-126">Para forzar que la clase <xref:System.Windows.Forms.SendKeys> use la implementación anterior, use el valor `"JournalHook"` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="84d88-126">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="84d88-127">Para enviar una pulsación de tecla a la misma aplicación</span><span class="sxs-lookup"><span data-stu-id="84d88-127">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="84d88-128">Llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> de la clase <xref:System.Windows.Forms.SendKeys> .</span><span class="sxs-lookup"><span data-stu-id="84d88-128">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="84d88-129">El control activo de la aplicación recibirá las pulsaciones de teclas especificadas.</span><span class="sxs-lookup"><span data-stu-id="84d88-129">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="84d88-130">El siguiente ejemplo de código usa <xref:System.Windows.Forms.SendKeys.Send%2A> para simular la tecla ENTRAR cuando el usuario hace doble clic en la superficie del formulario.</span><span class="sxs-lookup"><span data-stu-id="84d88-130">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="84d88-131">En este ejemplo se da por supuesto un <xref:System.Windows.Forms.Form> con un solo control <xref:System.Windows.Forms.Button> que tiene un índice de tabulación de 0.</span><span class="sxs-lookup"><span data-stu-id="84d88-131">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="84d88-132">Para enviar una pulsación de tecla a una aplicación diferente</span><span class="sxs-lookup"><span data-stu-id="84d88-132">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="84d88-133">Active la ventana de la aplicación que recibirá las pulsaciones de teclas y, después, llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> .</span><span class="sxs-lookup"><span data-stu-id="84d88-133">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="84d88-134">Como no hay ningún método administrado para activar otra aplicación, debe usar métodos nativos de Windows para forzar el foco en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="84d88-134">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="84d88-135">El ejemplo de código siguiente usa la invocación de la plataforma para llamar a los métodos `FindWindow` y `SetForegroundWindow` para activar la ventana de la aplicación Calculadora y, después, llama a <xref:System.Windows.Forms.SendKeys.SendWait%2A> para emitir una serie de cálculos a la aplicación Calculadora.</span><span class="sxs-lookup"><span data-stu-id="84d88-135">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="84d88-136">Los parámetros correctos de la llamada a `FindWindow` que busca la aplicación Calculadora varían en función de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="84d88-136">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="84d88-137">El código siguiente busca la aplicación Calculator en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="84d88-137">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="84d88-138">En [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], cambie el primer parámetro por "SciCalc".</span><span class="sxs-lookup"><span data-stu-id="84d88-138">On [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], change the first parameter to "SciCalc".</span></span> <span data-ttu-id="84d88-139">Puede usar la herramienta Spy ++, incluida con Visual Studio, para determinar los parámetros correctos.</span><span class="sxs-lookup"><span data-stu-id="84d88-139">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="84d88-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84d88-140">Example</span></span>

<span data-ttu-id="84d88-141">El ejemplo de código siguiente es la aplicación completa de los ejemplos de código anteriores.</span><span class="sxs-lookup"><span data-stu-id="84d88-141">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="84d88-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="84d88-142">Compiling the Code</span></span>

<span data-ttu-id="84d88-143">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="84d88-143">This example requires:</span></span>

- <span data-ttu-id="84d88-144">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="84d88-144">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="84d88-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="84d88-145">See also</span></span>

- [<span data-ttu-id="84d88-146">Datos proporcionados por el usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84d88-146">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
