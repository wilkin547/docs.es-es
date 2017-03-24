---
title: "C&#243;mo: Enviar cadenas a puertos serie en Visual Basic | Microsoft Docs"
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
  - "puertos, enviar cadenas"
  - "puertos serie, enviar cadenas"
  - "cadenas [Visual Basic], enviar a puertos serie"
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Enviar cadenas a puertos serie en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este tema se describe cómo utilizar `My.Computer.Ports` para enviar cadenas a los puertos serie del equipo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Ejemplo  
 Este ejemplo envía una cadena al puerto serie COM1.  Puede que necesite utilizar un puerto serie diferente de su equipo.  
  
 Utilice el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción.  Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro de un bloque `Try...Catch...Finally`.  
  
 El método <xref:System.IO.Ports.SerialPort.WriteLine%2A> envía los datos al puerto serie.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## Compilar el código  
  
-   Este ejemplo supone que el equipo está utilizando el puerto `COM1`.  
  
## Programación eficaz  
 Este ejemplo supone que el equipo está utilizando el puerto `COM1`; para una mayor flexibilidad, el código debería permitir al usuario seleccionar el puerto serie deseado en una lista de puertos disponibles.  Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Este ejemplo utiliza un bloque `Using` para asegurarse de que la aplicación cierra el puerto aun cuando produzca una excepción.  Para obtener más información, vea [Using \(Instrucción\)](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Cómo: Mostrar los puertos serie disponibles](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)