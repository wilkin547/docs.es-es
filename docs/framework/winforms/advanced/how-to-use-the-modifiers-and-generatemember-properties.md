---
title: 'Cómo: Utilizar las propiedades Modifiers y GenerateMember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 451c54bf6272b4fbff46b5298ba5b6a9290656e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Cómo: Utilizar las propiedades Modifiers y GenerateMember
Cuando se coloca un componente en un formulario Windows Forms, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`. El `GenerateMember` propiedad especifica si el Diseñador de Windows Forms genera una variable miembro para un componente. El `Modifiers` propiedad es el modificador de acceso que se asigna a la variable miembro. Si el valor de la `GenerateMember` propiedad es `false`, el valor de la `Modifiers` propiedad no tiene ningún efecto.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>Para especificar si un componente es un miembro del formulario  
  
1.  En el Diseñador de Windows Forms, abra el formulario.  
  
2.  Abra la **cuadro de herramientas**y en el formulario, coloque tres <xref:System.Windows.Forms.Button> controles.  
  
3.  Establecer el `GenerateMember` y `Modifiers` propiedades para cada <xref:System.Windows.Forms.Button> control según la tabla siguiente.  
  
    |Nombre del botón|Valor de GenerateMember|Valor de modificadores|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|No hay ningún cambio|  
  
4.  Compile la solución.  
  
5.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
6.  Abra la **Form1** nodo y en el **Editor de código**, abra el **Form1.Designer.vb** o **Form1.Designer.cs** archivo. Este archivo contiene el código emitido por el Diseñador de Windows Forms.  
  
7.  Encuentre las declaraciones para los tres botones. En el ejemplo de código siguiente se muestra las diferencias especificadas por el `GenerateMember` y `Modifiers` propiedades.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  De forma predeterminada, el Diseñador de Windows Forms asigna el `private` (`Friend` en Visual Basic) modificador a controles de contenedor como <xref:System.Windows.Forms.Panel>. Si la base de <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> tiene un control contenedor, no aceptará nuevos elementos secundarios en controles y formularios heredados. La solución consiste en cambiar el modificador del control contenedor base a `protected` o `public`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Button>  
 [Herencia visual de Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Tutorial: Demostración de la herencia visual](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
