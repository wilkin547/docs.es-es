---
title: Procedimiento para controlar errores y excepciones que se producen con el enlace de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 43e22f34f488f0ec7664587e194c026dedb87824
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651707"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>Procedimiento para controlar errores y excepciones que se producen con el enlace de datos
A menudo, las excepciones y los errores se producen en los objetos comerciales subyacentes cuando se enlazan a controles. Puede interceptar estos errores y excepciones y, después, recuperar o pasar la información de error al usuario controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete> para un componente <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> o <xref:System.Windows.Forms.CurrencyManager> determinado.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de código se muestra cómo controlar errores y excepciones que se producen durante una operación de enlace de datos. Muestra cómo interceptar los errores controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> de los objetos <xref:System.Windows.Forms.Binding>. Para interceptar errores y excepciones controlando este evento, debe habilitar el formato del enlace. Puede habilitar el formato al crear el enlace o al agregarlo a la colección de enlaces, o estableciendo la propiedad <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> en `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Cuando se ejecuta el código y se especifica una cadena vacía como nombre de elemento o un valor inferior a 100 como número de elemento, aparece un cuadro de mensaje. Este es el resultado de controlar el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> para estos enlaces de cuadro de texto.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [Componente BindingSource](bindingsource-component.md)
