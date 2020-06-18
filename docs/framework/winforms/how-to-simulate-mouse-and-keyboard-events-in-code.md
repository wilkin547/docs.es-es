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
ms.openlocfilehash: 9b453787f7fa7f5041f75e04d65557a0a3838bee
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904369"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a>Procedimiento para simular eventos del mouse y del teclado en el código

Windows Forms ofrece varias opciones para simular la entrada de mouse y de teclado mediante programación. En este tema se ofrece una introducción a estas opciones.

## <a name="simulating-mouse-input"></a>Simular la entrada de mouse

La mejor forma de simular eventos del mouse es llamar al método `On`*EventName* que genera el evento del mouse que quiere simular. Normalmente, esta opción solo es posible dentro de controles y formularios personalizados, porque los métodos que generan eventos están protegidos y no se puede acceder a ellos fuera del control o formulario. Por ejemplo, los siguientes pasos muestran cómo simular el clic con el botón secundario del mouse en el código.

#### <a name="to-programmatically-click-the-right-mouse-button"></a>Para hacer clic con el botón secundario del mouse mediante programación

1. Cree un <xref:System.Windows.Forms.MouseEventArgs> cuya propiedad <xref:System.Windows.Forms.MouseEventArgs.Button%2A> esté establecida en el valor <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .

2. Llame al método <xref:System.Windows.Forms.Control.OnMouseClick%2A> con este <xref:System.Windows.Forms.MouseEventArgs> como argumento.

Para más información sobre controles personalizados, vea [Desarrollar controles de Windows Forms en tiempo de diseño](./controls/developing-windows-forms-controls-at-design-time.md).

Hay otras maneras de simular la entrada de mouse. Por ejemplo, puede establecer mediante programación una propiedad de control que representa un estado que normalmente se establece mediante la entrada de mouse (como la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> del control <xref:System.Windows.Forms.CheckBox> ), o puede llamar directamente al delegado que está asociado al evento que quiere simular.

## <a name="simulating-keyboard-input"></a>Simular la entrada de teclado

Aunque puede simular la entrada del teclado con las estrategias descritas anteriormente para la entrada de mouse, Windows Forms también proporciona la clase <xref:System.Windows.Forms.SendKeys> para enviar pulsaciones de tecla a la aplicación activa.

> [!CAUTION]
> Si su aplicación está pensada para su uso internacional con distintos teclados, <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> puede producir resultados imprevisibles y debe evitarse.

> [!NOTE]
> La clase <xref:System.Windows.Forms.SendKeys> se ha actualizado para .NET Framework 3.0 para que se pueda usar en aplicaciones que se ejecutan en Windows Vista. La seguridad mejorada de Windows Vista (conocida como Control de cuentas de usuario o UAC) impide que la implementación anterior funcione según lo esperado.
>
> La clase <xref:System.Windows.Forms.SendKeys> es susceptible de tener problemas de temporización que algunos desarrolladores han tenido que solucionar. La implementación actualizada sigue siendo susceptible de tener problemas de temporización, pero es ligeramente más rápida y puede requerir cambios en las soluciones alternativas. La clase <xref:System.Windows.Forms.SendKeys> intenta usar primero la implementación anterior y, si se produce un error, usa la nueva implementación. Como resultado, la clase <xref:System.Windows.Forms.SendKeys> puede comportarse de manera diferente en los distintos sistemas operativos. Además, cuando la clase <xref:System.Windows.Forms.SendKeys> usa la nueva implementación, el método <xref:System.Windows.Forms.SendKeys.SendWait%2A> no esperará a que se procesen los mensajes cuando se envían a otro proceso.
>
> Si la aplicación depende de un comportamiento coherente independientemente del sistema operativo, puede forzar que la clase <xref:System.Windows.Forms.SendKeys> use la nueva implementación agregando la siguiente opción de configuración de la aplicación al archivo app.config.
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> Para forzar que la clase <xref:System.Windows.Forms.SendKeys> use la implementación anterior, use el valor `"JournalHook"` en su lugar.

#### <a name="to-send-a-keystroke-to-the-same-application"></a>Para enviar una pulsación de tecla a la misma aplicación

1. Llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> de la clase <xref:System.Windows.Forms.SendKeys> . El control activo de la aplicación recibirá las pulsaciones de teclas especificadas. El siguiente ejemplo de código usa <xref:System.Windows.Forms.SendKeys.Send%2A> para simular la tecla ENTRAR cuando el usuario hace doble clic en la superficie del formulario. En este ejemplo se da por supuesto un <xref:System.Windows.Forms.Form> con un solo control <xref:System.Windows.Forms.Button> que tiene un índice de tabulación de 0.

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a>Para enviar una pulsación de tecla a una aplicación diferente

1. Active la ventana de la aplicación que recibirá las pulsaciones de teclas y, después, llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> . Como no hay ningún método administrado para activar otra aplicación, debe usar métodos nativos de Windows para forzar el foco en otras aplicaciones. El ejemplo de código siguiente usa la invocación de la plataforma para llamar a los métodos `FindWindow` y `SetForegroundWindow` para activar la ventana de la aplicación Calculadora y, después, llama a <xref:System.Windows.Forms.SendKeys.SendWait%2A> para emitir una serie de cálculos a la aplicación Calculadora.

    > [!NOTE]
    > Los parámetros correctos de la llamada a `FindWindow` que busca la aplicación Calculadora varían en función de la versión de Windows.  El código siguiente busca la aplicación Calculator en Windows 7. En Windows Vista, cambie el primer parámetro por "SciCalc". Puede usar la herramienta Spy ++, incluida con Visual Studio, para determinar los parámetros correctos.

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente es la aplicación completa de los ejemplos de código anteriores.

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.

## <a name="see-also"></a>Consulte también

- [Datos proporcionados por el usuario en formularios Windows Forms](user-input-in-windows-forms.md)
