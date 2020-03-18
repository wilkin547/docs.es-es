---
title: 'Cómo: iniciar una aplicación y enviarle pulsaciones de teclas: Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919392"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="1e77a-102">Cómo: iniciar una aplicación y enviarle pulsaciones de teclas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e77a-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="1e77a-103">En este ejemplo se usa el método <xref:Microsoft.VisualBasic.Interaction.Shell%2A> para iniciar la aplicación de Bloc de notas y, después, se imprime una frase mediante el envío de pulsaciones de teclas con el método [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A).</span><span class="sxs-lookup"><span data-stu-id="1e77a-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="1e77a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e77a-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="1e77a-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1e77a-105">Robust programming</span></span>

<span data-ttu-id="1e77a-106">Si no se encuentra una aplicación con el identificador de proceso solicitado, se generará una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="1e77a-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1e77a-107">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1e77a-107">.NET Framework Security</span></span>

<span data-ttu-id="1e77a-108">La llamada a la función `Shell` requiere plena confianza (clase <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="1e77a-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e77a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e77a-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
