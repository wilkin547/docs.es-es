---
description: 'Más información acerca de: Procedimiento: para marcar a través de módems conectados a puertos serie en Visual Basic'
title: Procedimiento para marcar a través de módems conectados a puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: 016a3f768020c551c4f4ca7f5a097f4f1f9d07d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797710"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a>Cómo: Marcar a través de módems conectados a puertos serie en Visual Basic

En este tema se explica cómo usar `My.Computer.Ports` para llamar a un módem en Visual Basic.  
  
 Normalmente, el módem se conecta a uno de los puertos serie del equipo. Para que la aplicación se comunique con el módem, debe enviar los comandos al puerto serie adecuado.  
  
### <a name="to-dial-a-modem"></a>Para llamar un módem  
  
1. Determine a qué puerto serie está conectado el módem. En este ejemplo se presupone que el módem está en COM1.  
  
2. Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto. Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción. Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro de un bloque `Try...Catch...Finally`.  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. Establezca la propiedad `DtrEnable` para indicar que el equipo está listo para aceptar una transmisión de entrada procedente del módem.  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. Envíe el comando de marcar y el número de teléfono al módem a través del puerto serie por medio del método <xref:System.IO.Ports.SerialPort.Write%2A>.  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Conectividad y redes**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Este ejemplo requiere una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  

 En este ejemplo se presupone que el módem está conectado a COM1. Es recomendable que el código permita al usuario seleccionar el puerto serie deseado de una lista de puertos disponibles. Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).  
  
 En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción. Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).  
  
 En este ejemplo, la aplicación desconecta el puerto serie después de marcar el módem. En la realidad, querrá transferir datos al módem y desde él. Para obtener más información, vea [Cómo: Recibir cadenas de puertos serie](how-to-receive-strings-from-serial-ports.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedimiento para enviar cadenas a puertos serie](how-to-send-strings-to-serial-ports.md)
- [Procedimiento para recibir cadenas de puertos serie](how-to-receive-strings-from-serial-ports.md)
- [Procedimiento para mostrar los puertos serie disponibles](how-to-show-available-serial-ports.md)
