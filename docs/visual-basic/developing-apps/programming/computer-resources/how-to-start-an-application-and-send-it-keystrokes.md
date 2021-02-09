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
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="66cfe-103">Cómo: iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66cfe-103">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="66cfe-104">En este ejemplo se usa el método <xref:Microsoft.VisualBasic.Interaction.Shell%2A> para iniciar la aplicación de Bloc de notas y, después, se imprime una frase mediante el envío de pulsaciones de teclas con el método [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A).</span><span class="sxs-lookup"><span data-stu-id="66cfe-104">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="66cfe-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66cfe-105">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="66cfe-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="66cfe-106">Robust programming</span></span>

<span data-ttu-id="66cfe-107">Si no se encuentra una aplicación con el identificador de proceso solicitado, se generará una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="66cfe-107">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="66cfe-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66cfe-108">.NET Framework Security</span></span>

<span data-ttu-id="66cfe-109">La llamada a la función `Shell` requiere plena confianza (clase <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="66cfe-109">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="66cfe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="66cfe-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
