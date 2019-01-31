---
title: Procedimiento para iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 36d6110a9e0ccf20718e95e6d7601e21e8d8f22c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688394"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Procedimiento para iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)
En el siguiente ejemplo se usa la función `Shell` para iniciar la aplicación calculadora y, después, multiplicar dos números enviando pulsaciones de teclas mediante el método `My.Computer.Keyboard.SendKeys`.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Si no se encuentra una aplicación con el identificador de proceso solicitado, se producirá una excepción <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 La llamada a la función `Shell` requiere plena confianza (clase <xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
