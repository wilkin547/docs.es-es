---
title: Procedimiento para controlar la entrada de teclado en el formulario
description: Obtenga información sobre cómo controlar la entrada del teclado para su Windows Forms en el nivel de formulario, antes de que los mensajes lleguen a un control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: 6f0695b6f665a613e0e4e001a4f9bbfc09dd45ed
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904161"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a>Procedimiento para controlar la entrada de teclado en el formulario
Windows Forms permite controlar los mensajes del teclado en el nivel de formulario, antes de que los mensajes lleguen a un control. En este tema se muestra cómo realizar esta tarea.  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a>Para controlar un mensaje de teclado en el nivel de formulario  
  
- Controle los eventos <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del formulario de inicio y establezca la propiedad <xref:System.Windows.Forms.Form.KeyPreview%2A> del formulario en `true` para que el formulario reciba los mensajes del teclado antes de que lleguen a los controles del formulario. Para controlar el evento <xref:System.Windows.Forms.Control.KeyPress>, el siguiente código de ejemplo detecta todas las teclas numéricas y consume las teclas '1', '4' y '7'.  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código es toda la aplicación del ejemplo anterior. La aplicación incluye un <xref:System.Windows.Forms.TextBox> además de otros controles que permiten mover el foco desde el <xref:System.Windows.Forms.TextBox>. El evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.Form> principal consume '1', '4' y '7' y el evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.TextBox> consume '2', '5' y '8' mientras muestra las teclas restantes. Compare el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla de número mientras el <xref:System.Windows.Forms.TextBox> tiene el foco con el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla numérica mientras el foco está en otro de los controles.  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- [Entradas mediante teclado en una aplicación de Windows Forms](keyboard-input-in-a-windows-forms-application.md)
