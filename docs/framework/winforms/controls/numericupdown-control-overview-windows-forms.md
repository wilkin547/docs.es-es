---
title: Información general sobre el control NumericUpDown
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740797"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Información general sobre el control NumericUpDown (formularios Windows Forms)
El control <xref:System.Windows.Forms.NumericUpDown> es similar a una combinación de un cuadro de texto y un par de flechas en las que el usuario puede hacer clic para ajustar un valor. El control muestra y establece un valor numérico único a partir de una lista de opciones de valor numérico fijo. Para aumentar y disminuir el número, haga clic en las flechas arriba y abajo, presione las teclas de dirección arriba y abajo o escriba un número en la parte del cuadro de texto del control. Al hacer clic en la tecla de flecha arriba, el número se desplaza hacia el máximo; al hacer clic en la tecla de flecha abajo, el número se mueve hacia el mínimo.  
  
 Debido a su versátil funcionalidad, este control es una opción obvia, por ejemplo, si desea crear un control de volumen para una aplicación de reproducción de música. El control <xref:System.Windows.Forms.NumericUpDown> se utiliza en muchas aplicaciones del panel de control de Windows.  
  
## <a name="key-properties-and-methods"></a>Propiedades y métodos clave  
 Los números mostrados en el cuadro de texto del control pueden estar en una variedad de formatos, incluido el formato hexadecimal. Para obtener más información, vea [Cómo: establecer el formato del control NumericUpDown Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Las propiedades clave del control son <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valor predeterminado 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valor predeterminado 0) y <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valor predeterminado: 1). La propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> establece el número actual seleccionado en el control. La propiedad <xref:System.Windows.Forms.NumericUpDown.Increment%2A> establece la cantidad por la que ajusta el número cuando el usuario hace clic en una flecha arriba o abajo. Cuando el foco se desplaza fuera del control, cualquier entrada con tipo se valida con los valores numéricos mínimo y máximo. Puede aumentar la velocidad con que el control se desplaza por los números, cuando el usuario presiona continuamente la flecha arriba o abajo, con la propiedad <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>. Los métodos clave del control son <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown (control)](numericupdown-control-windows-forms.md)
- [Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
