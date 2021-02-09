---
description: 'Más información acerca de: Procedimiento: para enviar cadenas a puertos serie en Visual Basic'
title: Procedimiento para enviar cadenas a puertos serie
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: 66dedaab05090af2659701e57b37b4813447b8ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666490"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Cómo: Enviar cadenas a puertos serie en Visual Basic

En este tema se explica cómo usar `My.Computer.Ports` para enviar cadenas a los puertos serie del equipo en Visual Basic.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se envía una cadena al puerto serie COM1. Es posible que tenga que usar un puerto serie diferente en el equipo.  
  
 Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto. Para obtener más información, vea <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 El bloque `Using` permite a la aplicación cerrar el puerto serie aun cuando se genere una excepción. Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro un bloque `Try...Catch...Finally`.  
  
 El método <xref:System.IO.Ports.SerialPort.WriteLine%2A> envía los datos al puerto serie.  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En este ejemplo se presupone que el equipo usa `COM1`.  
  
## <a name="robust-programming"></a>Programación sólida  

 En este ejemplo se presupone que el equipo está usando `COM1`. Para obtener mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie deseado entre una lista de puertos disponibles. Para obtener más información, vea [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md) (Cómo: Mostrar los puertos serie disponibles en Visual Basic).  
  
 En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción. Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedimiento para marcar a través de módems conectados a puertos serie](how-to-dial-modems-attached-to-serial-ports.md)
- [Procedimiento para mostrar los puertos serie disponibles](how-to-show-available-serial-ports.md)
