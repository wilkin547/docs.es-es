---
title: "C&#243;mo: Mostrar los puertos serie disponibles en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Ports (objeto)"
  - "My.Computer.Ports.SerialPortNames (propiedad)"
  - "puertos, disponibilidad de puertos serie"
  - "puertos serie, disponibilidad"
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# C&#243;mo: Mostrar los puertos serie disponibles en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este tema se describe cómo utilizar `My.Computer.Ports` para mostrar los puertos serie disponibles del equipo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Para permitir que un usuario seleccione el puerto que desea utilizar, los nombres de los puertos serie se colocan en un control <xref:System.Windows.Forms.ListBox>.  
  
## Ejemplo  
 Este ejemplo recorre todas las cadenas que devuelve la propiedad `My.Computer.Ports.SerialPortNames`.  Estas cadenas son los nombres de los puertos serie disponibles en el equipo.  
  
 Normalmente, un usuario selecciona el puerto serie que la aplicación debe utilizar en la lista de puertos disponibles.  En este ejemplo, los nombres de puertos serie se almacenan en un control <xref:System.Windows.Forms.ListBox>.  Para obtener más información, vea [ListBox \(Control\)](../Topic/ListBox%20Control%20\(Windows%20Forms\).md).  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia de proyecto a System.Windows.Forms.dll.  
  
-   Acceso a los miembros del espacio de nombres <xref:System.Windows.Forms>.  Agregar una instrucción `Imports` si no se incluyen nombres de miembro completos en el código.  Para obtener más información, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
-   Que el formulario tenga un control <xref:System.Windows.Forms.ListBox> denominado `ListBox1`.  
  
## Programación eficaz  
 No tiene que utilizar el control <xref:System.Windows.Forms.ListBox> para mostrar los nombres de los puertos serie disponibles.  En su lugar, puede utilizar un control <xref:System.Windows.Forms.ComboBox> u otro control.  Si la aplicación no necesita una respuesta del usuario, puede utilizar un control <xref:System.Windows.Forms.TextBox> para mostrar la información.  
  
> [!NOTE]
>  Es posible que los nombres de puerto devueltos por `My.Computer.Ports.SerialPortNames` sean incorrectos cuando se ejecuta en Windows 98.  Para evitar que se produzcan errores en la aplicación, use el control de excepciones, como la instrucción `Try...Catch...Finally` o la instrucción `Using`, cuando utilice los nombres de puerto para abrir los puertos.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Cómo: Enviar cadenas a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Cómo: Recibir cadenas de puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)