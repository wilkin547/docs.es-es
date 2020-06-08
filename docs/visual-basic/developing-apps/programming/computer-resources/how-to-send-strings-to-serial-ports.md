---
title: 'Cómo: Enviar cadenas a puertos serie'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: f78df9cf1bd75432ea645c4dcc06498915ceee49
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360298"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Cómo: Enviar cadenas a puertos serie en Visual Basic

En este tema se explica cómo usar `My.Computer.Ports` para enviar cadenas a los puertos serie del equipo en Visual Basic.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se envía una cadena al puerto serie COM1. Es posible que tenga que usar un puerto serie diferente en el equipo.  
  
 Use el método `My.Computer.Ports.OpenSerialPort` para obtener una referencia al puerto. Para obtener más información, consulta <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 El bloque `Using` permite a la aplicación cerrar el puerto serie aunque se genere una excepción. Todo el código que manipula el puerto serie debe aparecer dentro de este bloque o dentro un bloque `Try...Catch...Finally`.  
  
 El método <xref:System.IO.Ports.SerialPort.WriteLine%2A> envía los datos al puerto serie.  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En este ejemplo se presupone que el equipo usa `COM1`.  
  
## <a name="robust-programming"></a>Programación sólida  

 En este ejemplo se presupone que el equipo está usando `COM1`. Para obtener mayor flexibilidad, el código debe permitir al usuario seleccionar el puerto serie deseado entre una lista de puertos disponibles. Para obtener más información, vea [Cómo: Mostrar los puertos serie disponibles en Visual Basic](how-to-show-available-serial-ports.md).  
  
 En este ejemplo se usa un bloque `Using` para asegurarse de que la aplicación cierra el puerto incluso si se produce una excepción. Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Marcar a través de módems conectados a puertos serie](how-to-dial-modems-attached-to-serial-ports.md)
- [Mostrar los puertos serie disponibles](how-to-show-available-serial-ports.md)
