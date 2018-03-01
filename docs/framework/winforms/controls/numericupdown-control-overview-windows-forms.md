---
title: "Información general sobre el control NumericUpDown (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 067a8862ee991213e584819e1cf99eddde06e2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a>Información general sobre el control NumericUpDown (formularios Windows Forms)
El <xref:System.Windows.Forms.NumericUpDown> control es similar a una combinación de un cuadro de texto y un par de flechas en las que el usuario puede hacer clic para ajustar un valor. El control muestra y establece un valor numérico único en una lista de opciones de valor numérico fijas. El usuario puede aumentar y reducir el número, haga clic en arriba y abajo, presionando las teclas de dirección arriba y abajo, o escriba un número en el elemento de cuadro de texto del control. Al presionar la tecla flecha arriba desplaza el número en el valor máximo; al presionar la tecla de flecha abajo mueve el número hacia el valor mínimo.  
  
 Debido a su versátil funcionalidad, este control es una opción obvia, por ejemplo, si desea crear un control de volumen para una aplicación de Reproductor de música. El <xref:System.Windows.Forms.NumericUpDown> control se utiliza en muchas aplicaciones de Panel de Control de Windows.  
  
## <a name="key-properties-and-methods"></a>Métodos y propiedades claves  
 Los números mostrados en el cuadro de texto del control pueden estar en una variedad de formatos, incluidos los hexadecimales. Para obtener más información, consulte [Cómo: establecer el formato para el NumericUpDown Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Las propiedades principales del control son <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valor predeterminado es 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valor predeterminado es 0), y <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valor predeterminado 1). El <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad establece el número seleccionado actualmente en el control. El <xref:System.Windows.Forms.NumericUpDown.Increment%2A> propiedad establece la cantidad que el número se ajusta cuando el usuario hace clic en un arriba o flecha abajo. Cuando el foco se desplaza fuera del control, ninguna entrada con tipo se validarán con los valores numéricos de mínimos y máximo. Puede aumentar la velocidad que el control se mueve a través de números, cuando el usuario presiona continuamente arriba o flecha abajo, con el <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> propiedad. Los métodos principales del control son <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown (control)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
