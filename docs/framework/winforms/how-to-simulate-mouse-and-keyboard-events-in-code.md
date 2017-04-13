---
title: "C&#243;mo: Simular eventos del mouse y del teclado en el c&#243;digo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "teclados, simulación de evento"
  - "entrada del usuario, simulación"
  - "SendKeys, uso"
  - "clics del mouse, simulación"
  - "mouse, simulación de evento"
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Simular eventos del mouse y del teclado en el c&#243;digo
Windows Forms ofrece varias opciones para simular la entrada de mouse y de teclado mediante programación. En este tema se ofrece una introducción a estas opciones.  
  
## Simular la entrada de mouse  
 La mejor forma de simular eventos del mouse es llamar al método `On`*EventName* que genera el evento del mouse que quiere simular. Normalmente, esta opción solo es posible dentro de controles y formularios personalizados, porque los métodos que generan eventos están protegidos y no se puede acceder a ellos fuera del control o formulario. Por ejemplo, los siguientes pasos muestran cómo simular el clic con el botón secundario del mouse en el código.  
  
#### Para hacer clic con el botón secundario del mouse mediante programación  
  
1.  Cree un <xref:System.Windows.Forms.MouseEventArgs> cuya propiedad <xref:System.Windows.Forms.MouseEventArgs.Button%2A> esté establecida en el valor <xref:System.Windows.Forms.MouseButtons?displayProperty=fullName>.  
  
2.  Llame al método <xref:System.Windows.Forms.Control.OnMouseClick%2A> con este <xref:System.Windows.Forms.MouseEventArgs> como argumento.  
  
 Para obtener más información sobre los controles personalizados, consulte [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).  
  
 Hay otras maneras de simular la entrada de mouse. Por ejemplo, puede establecer mediante programación una propiedad de control que representa un estado que normalmente se establece mediante la entrada de mouse \(como la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> del control <xref:System.Windows.Forms.CheckBox>\), o puede llamar directamente al delegado que está asociado al evento que quiere simular.  
  
## Simular la entrada de teclado  
 Aunque puede simular la entrada del teclado con las estrategias descritas anteriormente para la entrada de mouse, Windows Forms también proporciona la clase <xref:System.Windows.Forms.SendKeys> para enviar pulsaciones de tecla a la aplicación activa.  
  
> [!CAUTION]
>  Si su aplicación está pensada para su uso internacional con distintos teclados, <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=fullName> puede producir resultados imprevisibles y debe evitarse.  
  
> [!NOTE]
>  La clase <xref:System.Windows.Forms.SendKeys> se ha actualizado para .NET Framework 3.0 para que se pueda usar en aplicaciones que se ejecutan en Windows Vista. La seguridad mejorada de Windows Vista \(conocida como Control de cuentas de usuario o UAC\) impide que la implementación anterior funcione según lo esperado.  
>   
>  La clase <xref:System.Windows.Forms.SendKeys> es susceptible de tener problemas de temporización que algunos desarrolladores han tenido que solucionar. La implementación actualizada sigue siendo susceptible de tener problemas de temporización, pero es ligeramente más rápida y puede requerir cambios en las soluciones alternativas. La clase <xref:System.Windows.Forms.SendKeys> intenta usar primero la implementación anterior y, si se produce un error, usa la nueva implementación. Como resultado, la clase <xref:System.Windows.Forms.SendKeys> puede comportarse de manera diferente en los distintos sistemas operativos. Además, cuando la clase <xref:System.Windows.Forms.SendKeys> usa la nueva implementación, el método <xref:System.Windows.Forms.SendKeys.SendWait%2A> no esperará a que se procesen los mensajes cuando se envían a otro proceso.  
>   
>  Si la aplicación depende de un comportamiento coherente independientemente del sistema operativo, puede forzar que la clase <xref:System.Windows.Forms.SendKeys> use la nueva implementación agregando la siguiente opción de configuración de la aplicación al archivo app.config.  
>   
>  `<appSettings>`  
>   
>  `<add key="SendKeys" value="SendInput"/>`  
>   
>  `</appSettings>`  
>   
>  Para forzar que la clase <xref:System.Windows.Forms.SendKeys> use la implementación anterior, use el valor `"JournalHook"` en su lugar.  
  
#### Para enviar una pulsación de tecla a la misma aplicación  
  
1.  Llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> de la clase <xref:System.Windows.Forms.SendKeys>. El control activo de la aplicación recibirá las pulsaciones de teclas especificadas. El siguiente ejemplo de código usa <xref:System.Windows.Forms.SendKeys.Send%2A> para simular la tecla ENTRAR cuando el usuario hace doble clic en la superficie del formulario. En este ejemplo se da por supuesto un <xref:System.Windows.Forms.Form> con un solo control <xref:System.Windows.Forms.Button> que tiene un índice de tabulación de 0.  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]  
  
#### Para enviar una pulsación de tecla a una aplicación diferente  
  
1.  Active la ventana de la aplicación que recibirá las pulsaciones de teclas y, después, llame al método <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A>. Como no hay ningún método administrado para activar otra aplicación, debe usar métodos nativos de Windows para forzar el foco en otras aplicaciones. El ejemplo de código siguiente usa la invocación de la plataforma para llamar a los métodos `FindWindow` y `SetForegroundWindow` para activar la ventana de la aplicación Calculadora y, después, llama a <xref:System.Windows.Forms.SendKeys.SendWait%2A> para emitir una serie de cálculos a la aplicación Calculadora.  
  
    > [!NOTE]
    >  Los parámetros correctos de la llamada a `FindWindow` que busca la aplicación Calculadora varían en función de la versión de Windows.  El código siguiente busca la aplicación Calculadora en [!INCLUDE[win7](../../../includes/win7-md.md)]. En [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], cambie el primer parámetro por "SciCalc". Puede usar la herramienta Spy \+\+, incluida con Visual Studio, para determinar los parámetros correctos.  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]  
  
## Ejemplo  
 El ejemplo de código siguiente es la aplicación completa de los ejemplos de código anteriores.  
  
 [!code-cpp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener más información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 [User Input in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)