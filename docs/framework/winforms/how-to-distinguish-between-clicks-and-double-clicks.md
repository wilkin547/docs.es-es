---
title: 'Cómo: Distinguir operaciones de clic y de doble clic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
ms.openlocfilehash: 6c8603df5a844fb93db0555b605f16235b9dff54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539729"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a>Cómo: Distinguir operaciones de clic y de doble clic
Normalmente, un único *clic* inicia una acción de la interfaz de usuario (UI) y un *doble clic* extiende la acción. Por ejemplo, un clic normalmente selecciona un elemento y un doble clic edita el elemento seleccionado. Sin embargo, los eventos de clic de Windows Forms no se adaptan fácilmente un escenario en el que un clic y un doble clic realizan acciones incompatibles, ya que una acción asociada al evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> se realiza antes de la acción asociada al evento <xref:System.Windows.Forms.Control.DoubleClick> o <xref:System.Windows.Forms.Control.MouseDoubleClick>. Este tema se muestran dos soluciones a este problema. Una solución es controlar el evento de doble clic y revertir las acciones en el control del evento de clic. En raras ocasiones, puede que necesite simular el comportamiento de clic y doble clic controlando el evento <xref:System.Windows.Forms.Control.MouseDown> y usando las propiedades <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> y <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> de la clase <xref:System.Windows.Forms.SystemInformation>. Mida el tiempo entre los clics y si se produce un segundo clic antes de alcanzar el valor de <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> y el clic en está dentro de un rectángulo definido por <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, realice la acción de doble clic; de lo contrario, realice la acción de clic.  
  
### <a name="to-roll-back-a-click-action"></a>Para revertir una acción de clic  
  
-   Asegúrese de que el control con el que trabaja tiene un comportamiento de doble clic estándar. Si no es así, habilite el control con el método <xref:System.Windows.Forms.Control.SetStyle%2A>. Controle el evento de doble clic y revierta la acción de clic, así como la acción de doble clic. En el ejemplo de código siguiente se muestra cómo crear un botón personalizado con el doble clic habilitado, y cómo revertir la acción de clic en el código de control de eventos de doble clic.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a>Para distinguir entre los clics en el evento MouseDown  
  
-   Controle el evento <xref:System.Windows.Forms.Control.MouseDown> y determine la ubicación y el intervalo de tiempo entre los clics usando las propiedades <xref:System.Windows.Forms.SystemInformation> adecuadas y un componente <xref:System.Windows.Forms.Timer>. Realice las acciones apropiadas en función de si tiene lugar un clic o un doble clic. En el ejemplo de código siguiente se muestra cómo hacer esto.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para estos ejemplos se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar estos ejemplos desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar estos ejemplos en Visual Studio pegando el código en proyectos nuevos.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 [Entradas mediante el mouse en una aplicación de Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
