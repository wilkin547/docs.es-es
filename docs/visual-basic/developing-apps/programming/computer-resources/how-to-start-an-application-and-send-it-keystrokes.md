---
description: 'Más información acerca de: Cómo: iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)'
title: 'Cómo: iniciar una aplicación y enviarle pulsaciones de teclas: Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: ea54b940b528e0833d9c7a6cbef67f65a4cb4f6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666464"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Cómo: iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)

En este ejemplo se usa el método <xref:Microsoft.VisualBasic.Interaction.Shell%2A> para iniciar la aplicación de Bloc de notas y, después, se imprime una frase mediante el envío de pulsaciones de teclas con el método [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A).

## <a name="example"></a>Ejemplo

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a>Programación sólida

Si no se encuentra una aplicación con el identificador de proceso solicitado, se generará una excepción <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework

La llamada a la función `Shell` requiere plena confianza (clase <xref:System.Security.SecurityException>).

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
