---
title: "Cómo: Recibir cadenas de puertos serie en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 500a6c651f6eb991eb9fefef601d0f593a38352f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Cómo: Recibir cadenas de puertos serie en Visual Basic
En este tema se describe cómo usar `My.Computer.Ports` para recibir cadenas de los puertos serie del equipo en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
### <a name="to-receive-strings-from-the-serial-port"></a>Para recibir cadenas del puerto serie  
  
1.  Inicialice la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  Determine el puerto serie que debe proporcionar las cadenas. En este ejemplo se da por supuesto que es `COM1`.  
  
3.  Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto. Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     El bloque `Try...Catch...Finally` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción. Todo el código que manipula el puerto serie debe aparecer dentro de este bloque.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  Cree un bucle `Do` que lea líneas de texto hasta que no haya más líneas disponibles.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  Use el método <xref:System.IO.Ports.SerialPort.ReadLine%2A> para leer la siguiente línea de texto disponible desde el puerto serie.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  Use una instrucción `If` para determinar si el método <xref:System.IO.Ports.SerialPort.ReadLine%2A> devuelve `Nothing` (lo que indica que no hay más texto disponible). Si devuelve `Nothing`, salga del bucle `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  Agregue un bloque `Else` a la instrucción `If` para controlar el caso si la cadena se lee realmente. El bloque anexa la cadena del puerto serie a la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  Devolver la cadena.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Conectividad y redes**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 En este ejemplo se presupone que el equipo usa `COM1`.  
  
## <a name="robust-programming"></a>Programación sólida  
 En este ejemplo se presupone que el equipo usa `COM1`. Para brindar mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie que quiera de una lista de puertos disponibles. Para obtener más información, vea [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).  
  
 En este ejemplo se usa un bloque `Try...Catch...Finally` para asegurarse de que la aplicación cierra el puerto y para capturar las excepciones de tiempo de espera. Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Cómo: Marcar a través de módems conectados a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Cómo: Enviar cadenas a puertos serie](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Mostrar los puertos serie disponibles](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

