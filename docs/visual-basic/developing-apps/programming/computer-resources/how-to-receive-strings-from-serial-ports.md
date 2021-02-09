---
description: 'Más información acerca de: Procedimiento: para recibir cadenas de puertos serie en Visual Basic'
title: Procedimiento para recibir cadenas de puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 5e6de24392c6102b6dc613d909c827cc32f513d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666542"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Cómo: Recibir cadenas de puertos serie en Visual Basic

En este tema se explica cómo usar `My.Computer.Ports` para recibir cadenas de los puertos serie del equipo en Visual Basic.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>Para recibir cadenas del puerto serie  
  
1. Inicialice la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. Determine el puerto serie que debe proporcionar las cadenas. En este ejemplo se da por supuesto que es `COM1`.  
  
3. Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto. Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     El bloque `Try...Catch...Finally` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción. Todo el código que manipula el puerto serie debe aparecer dentro de este bloque.  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. Cree un bucle `Do` que lea líneas de texto hasta que no haya más líneas disponibles.  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. Use el método <xref:System.IO.Ports.SerialPort.ReadLine> para leer la siguiente línea de texto disponible desde el puerto serie.  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. Use una instrucción `If` para determinar si el método <xref:System.IO.Ports.SerialPort.ReadLine> devuelve `Nothing` (lo que indica que no hay más texto disponible). Si devuelve `Nothing`, salga del bucle `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. Agregue un bloque `Else` a la instrucción `If` para controlar el caso si la cadena se lee realmente. El bloque anexa la cadena del puerto serie a la cadena de devolución.  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. Devolver la cadena.  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Conectividad y redes**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  

 En este ejemplo se presupone que el equipo usa `COM1`.  
  
## <a name="robust-programming"></a>Programación sólida  

 En este ejemplo se presupone que el equipo usa `COM1`. Para brindar mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie que quiera de una lista de puertos disponibles. Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).  
  
 En este ejemplo se usa un bloque `Try...Catch...Finally` para asegurarse de que la aplicación cierra el puerto y para capturar las excepciones de tiempo de espera. Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedimiento para marcar a través de módems conectados a puertos serie](how-to-dial-modems-attached-to-serial-ports.md)
- [Procedimiento para enviar cadenas a puertos serie](how-to-send-strings-to-serial-ports.md)
- [Procedimiento para mostrar los puertos serie disponibles](how-to-show-available-serial-ports.md)
