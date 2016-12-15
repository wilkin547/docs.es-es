---
title: "C&#243;mo: Recibir cadenas de puertos serie en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources (objeto)"
  - "puertos serie, recuperar cadenas"
  - "cadenas [Visual Basic], recuperar de puertos serie"
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Recibir cadenas de puertos serie en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este tema se explica cómo utilizar `My.Computer.Ports` para recibir cadenas de los puertos serie del equipo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Para recibir cadenas del puerto serie  
  
1.  Inicialice la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  Determine qué puerto serie debe proporcionar las cadenas.  Este ejemplo supone que es `COM1`.  
  
3.  Utilice el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     El bloque `Try...Catch...Finally` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.  Todo el código que manipula el puerto serie debe aparecer dentro de este bloque.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  Cree un bucle `Do` para leer las líneas de texto hasta que no queden líneas disponibles.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  Utilice el método <xref:System.IO.Ports.SerialPort.ReadLine%2A> para leer en el puerto serie la siguiente línea de texto disponible.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  Utilice una instrucción `If` para determinar si el método <xref:System.IO.Ports.SerialPort.ReadLine%2A> devuelve `Nothing` \(lo que significa que no hay más texto disponible\).  Si devuelve `Nothing`, salga del bucle `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  Agregue un bloque `Else` a la instrucción `If` para controlar el caso de que realmente se lea la cadena.  El bloque anexa la cadena del puerto serie a la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  Devuelva la cadena.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## Ejemplo  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Compilar el código  
 Este ejemplo supone que el equipo está utilizando el puerto `COM1`.  
  
## Programación eficaz  
 Este ejemplo supone que el equipo está utilizando el puerto `COM1`.  Para mayor flexibilidad, el código debería permitir al usuario seleccionar el puerto serie deseado en una lista de puertos disponibles.  Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 En este ejemplo se utiliza un bloque `Try...Catch...Finally` para asegurarse de que la aplicación cierra el puerto y detectar cualquier excepción de tiempo de espera.  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Cómo: Enviar cadenas a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Cómo: Mostrar los puertos serie disponibles](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)