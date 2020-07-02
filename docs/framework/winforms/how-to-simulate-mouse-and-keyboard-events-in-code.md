---
title: Procedimiento para simular eventos del mouse y del teclado en el código
description: Aprenda a usar las opciones Windows Forms proporciona para simular mediante programación las entradas del mouse y del teclado.
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
ms.openlocfilehash: 3c60533479352151ac4f28690413ebc7d8e5879d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619252"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="5a671-103">Procedimiento para simular eventos del mouse y del teclado en el código</span><span class="sxs-lookup"><span data-stu-id="5a671-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="5a671-104">Windows Forms ofrece varias opciones para simular la entrada de mouse y de teclado mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5a671-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="5a671-105">En este tema se ofrece una introducción a estas opciones.</span><span class="sxs-lookup"><span data-stu-id="5a671-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="5a671-106">Simular la entrada de mouse</span><span class="sxs-lookup"><span data-stu-id="5a671-106">Simulating Mouse Input</span></span>

<span data-ttu-id="5a671-107">La mejor forma de simular eventos del mouse es llamar al método `On`*EventName* que genera el evento del mouse que quiere simular.</span><span class="sxs-lookup"><span data-stu-id="5a671-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="5a671-108">Normalmente, esta opción solo es posible dentro de controles y formularios personalizados, porque los métodos que generan eventos están protegidos y no se puede acceder a ellos fuera del control o formulario.</span><span class="sxs-lookup"><span data-stu-id="5a671-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="5a671-109">Por ejemplo, los siguientes pasos muestran cómo simular el clic con el botón secundario del mouse en el código.</span><span class="sxs-lookup"><span data-stu-id="5a671-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="5a671-110">Para hacer clic con el botón secundario del mouse mediante programación</span><span class="sxs-lookup"><span data-stu-id="5a671-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="5a671-111">Cree un <xref:System.Windows.Forms.MouseEventArgs> cuya propiedad <xref:System.Windows.Forms.MouseEventArgs.Button%2A> esté establecida en el valor <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5a671-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="5a671-112">Llame al método <xref:System.Windows.Forms.Control.OnMouseClick%2A> con este <xref:System.Windows.Forms.MouseEventArgs> como argumento.</span><span class="sxs-lookup"><span data-stu-id="5a671-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="5a671-113">Para más información sobre controles personalizados, vea [Desarrollar controles de Windows Forms en tiempo de diseño](./controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="5a671-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="5a671-114">Hay otras maneras de simular la entrada de mouse.</span><span class="sxs-lookup"><span data-stu-id="5a671-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="5a671-115">Por ejemplo, puede establecer mediante programación una propiedad de control que representa un estado que normalmente se establece mediante la entrada de mouse (como la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> del control <xref:System.Windows.Forms.CheckBox> ), o puede llamar directamente al delegado que está asociado al evento que quiere simular.</span><span class="sxs-lookup"><span data-stu-id="5a671-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="5a671-116">Simular la entrada de teclado</span><span class="sxs-lookup"><span data-stu-id="5a671-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="5a671-117">Aunque puede simular la entrada del teclado con las estrategias descritas anteriormente para la entrada de mouse, Windows Forms también proporciona la clase <xref:System.Windows.Forms.SendKeys> para enviar pulsaciones de tecla a la aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="5a671-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="5a671-118">Si su aplicación está pensada para su uso internacional con distintos teclados, <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> puede producir resultados imprevisibles y debe evitarse.</span><span class="sxs-lookup"><span data-stu-id="5a671-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="5a671-119">La clase <xref:System.Windows.Forms.SendKeys> se ha actualizado para .NET Framework 3.0 para que se pueda usar en aplicaciones que se ejecutan en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="5a671-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="5a671-120">La seguridad mejorada de Windows Vista (conocida como Control de cuentas de usuario o UAC) impide que la implementación anterior funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="5a671-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="5a671-121">La clase <xref:System.Windows.Forms.SendKeys> es susceptible de tener problemas de temporización que algunos desarrolladores han tenido que solucionar.</span><span class="sxs-lookup"><span data-stu-id="5a671-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="5a671-122">La implementación actualizada sigue siendo susceptible de tener problemas de temporización, pero es ligeramente más rápida y puede requerir cambios en las soluciones alternativas.</span><span class="sxs-lookup"><span data-stu-id="5a671-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="5a671-123">La clase <xref:System.Windows.Forms.SendKeys> intenta usar primero la implementación anterior y, si se produce un error, usa la nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="5a671-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="5a671-124">Como resultado, la clase <xref:System.Windows.Forms.SendKeys> puede comportarse de manera diferente en los distintos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="5a671-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="5a671-125">Además, cuando la clase <xref:System.Windows.Forms.SendKeys> usa la nueva implementación, el método <xref:System.Windows.Forms.SendKeys.SendWait%2A> no esperará a que se procesen los mensajes cuando se envían a otro proceso.</span><span class="sxs-lookup"><span data-stu-id="5a671-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="5a671-126">Si la aplicación depende de un comportamiento coherente independientemente del sistema operativo, puede forzar que la clase <xref:System.Windows.Forms.SendKeys> use la nueva implementación agregando la siguiente opción de configuración de la aplicación al archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="5a671-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="5a671-127">Para forzar que la clase <xref:System.Windows.Forms.SendKeys> use la implementación anterior, use el valor `"JournalHook"` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a671-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="5a671-128">Para enviar una pulsación de tecla a la misma aplicación</span><span class="sxs-lookup"><span data-stu-id="5a671-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="5a671-129">Llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> de la clase <xref:System.Windows.Forms.SendKeys> .</span><span class="sxs-lookup"><span data-stu-id="5a671-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="5a671-130">El control activo de la aplicación recibirá las pulsaciones de teclas especificadas.</span><span class="sxs-lookup"><span data-stu-id="5a671-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="5a671-131">El siguiente ejemplo de código usa <xref:System.Windows.Forms.SendKeys.Send%2A> para simular la tecla ENTRAR cuando el usuario hace doble clic en la superficie del formulario.</span><span class="sxs-lookup"><span data-stu-id="5a671-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="5a671-132">En este ejemplo se da por supuesto un <xref:System.Windows.Forms.Form> con un solo control <xref:System.Windows.Forms.Button> que tiene un índice de tabulación de 0.</span><span class="sxs-lookup"><span data-stu-id="5a671-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="5a671-133">Para enviar una pulsación de tecla a una aplicación diferente</span><span class="sxs-lookup"><span data-stu-id="5a671-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="5a671-134">Active la ventana de la aplicación que recibirá las pulsaciones de teclas y, después, llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> .</span><span class="sxs-lookup"><span data-stu-id="5a671-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="5a671-135">Como no hay ningún método administrado para activar otra aplicación, debe usar métodos nativos de Windows para forzar el foco en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5a671-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="5a671-136">El ejemplo de código siguiente usa la invocación de la plataforma para llamar a los métodos `FindWindow` y `SetForegroundWindow` para activar la ventana de la aplicación Calculadora y, después, llama a <xref:System.Windows.Forms.SendKeys.SendWait%2A> para emitir una serie de cálculos a la aplicación Calculadora.</span><span class="sxs-lookup"><span data-stu-id="5a671-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a671-137">Los parámetros correctos de la llamada a `FindWindow` que busca la aplicación Calculadora varían en función de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="5a671-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="5a671-138">El código siguiente busca la aplicación Calculator en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5a671-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="5a671-139">En Windows Vista, cambie el primer parámetro por "SciCalc".</span><span class="sxs-lookup"><span data-stu-id="5a671-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="5a671-140">Puede usar la herramienta Spy ++, incluida con Visual Studio, para determinar los parámetros correctos.</span><span class="sxs-lookup"><span data-stu-id="5a671-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="5a671-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a671-141">Example</span></span>

<span data-ttu-id="5a671-142">El ejemplo de código siguiente es la aplicación completa de los ejemplos de código anteriores.</span><span class="sxs-lookup"><span data-stu-id="5a671-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="5a671-143">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5a671-143">Compiling the Code</span></span>

<span data-ttu-id="5a671-144">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5a671-144">This example requires:</span></span>

- <span data-ttu-id="5a671-145">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5a671-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a671-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a671-146">See also</span></span>

- [<span data-ttu-id="5a671-147">Datos proporcionados por el usuario en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a671-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
