---
title: Información general sobre el control NumericUpDown (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 218eb685e546acac76a18450612a1601ab87276b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109881"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Información general sobre el control NumericUpDown (formularios Windows Forms)
El <xref:System.Windows.Forms.NumericUpDown> control es similar a una combinación de un cuadro de texto y un par de flechas en las que el usuario puede hacer clic para ajustar un valor. El control muestra y establece un valor numérico único de una lista de opciones de valor numérico fijas. El usuario puede aumentar y disminuir el número, haga clic en arriba y abajo las flechas, presionando las teclas de dirección arriba y abajo, o escribiendo un número en el elemento de cuadro de texto del control. Al presionar la tecla flecha arriba desplaza el número en el valor máximo; al hacer clic en la tecla flecha abajo mueve el número hacia el valor mínimo.  
  
 Debido a su funcionalidad versátil, este control es una elección obvia, por ejemplo, si desea crear un control de volumen para una aplicación de Reproductor de música. El <xref:System.Windows.Forms.NumericUpDown> control se usa en muchas aplicaciones del Panel de Control de Windows.  
  
## <a name="key-properties-and-methods"></a>Los métodos y propiedades de clave  
 Los números que aparecen en el cuadro de texto del control pueden estar en una variedad de formatos, incluidos hexadecimales. Para obtener más información, vea [Cómo: Establecer el formato de la Windows Forms Control NumericUpDown](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Las propiedades claves del control son <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valor predeterminado es 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valor predeterminado es 0), y <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valor predeterminado 1). El <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad establece el número seleccionado actualmente en el control. El <xref:System.Windows.Forms.NumericUpDown.Increment%2A> propiedad establece la cantidad que se ajusta el número cuando el usuario hace clic en arriba o flecha abajo. Cuando el foco se desplaza fuera del control, se validará cualquier entrada con tipo frente a los valores numéricos de mínimos y máximo. Puede aumentar la velocidad que el control se desplaza por los números, cuando el usuario presiona arriba o flecha abajo, con el <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> propiedad. Los métodos clave del control son <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown (control)](numericupdown-control-windows-forms.md)
- [Cómo: Establecer el formato del control NumericUpDown de formularios de Windows](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
