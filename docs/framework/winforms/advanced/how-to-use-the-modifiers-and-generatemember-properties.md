---
title: Filtrar Utilice las propiedades Modifiers y GenerateMember
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
ms.openlocfilehash: 277d2bdebc1d3b85efb70510b8acd34ed3a91087
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710802"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Filtrar Utilice las propiedades Modifiers y GenerateMember
Cuando se coloca un componente en un formulario de Windows, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`. El `GenerateMember` propiedad especifica que cuando el Diseñador de Windows Forms genera una variable miembro para un componente. El `Modifiers` propiedad es el modificador de acceso asignado a esa variable de miembro. Si el valor de la `GenerateMember` propiedad es `false`, el valor de la `Modifiers` propiedad no tiene ningún efecto.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>Para especificar si un componente es un miembro del formulario  
  
1.  En el Diseñador de formularios de Windows, abra el formulario.  
  
2.  Abra el **cuadro de herramientas**y en el formulario, coloque tres <xref:System.Windows.Forms.Button> controles.  
  
3.  Establecer el `GenerateMember` y `Modifiers` propiedades para cada <xref:System.Windows.Forms.Button> control según la tabla siguiente.  
  
    |Nombre del botón|Valor de GenerateMember|Valor de modificadores|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Sin cambios|  
  
4.  Compile la solución.  
  
5.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
6.  Abra el **Form1** nodo y en el **Editor de código**, abra el **Form1.Designer.vb** o **Form1.Designer.cs** archivo. Este archivo contiene el código emitido por el Diseñador de formularios de Windows.  
  
7.  Busque las declaraciones de los tres botones. El ejemplo de código siguiente muestra las diferencias especificadas por el `GenerateMember` y `Modifiers` propiedades.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  De forma predeterminada, el Diseñador de formularios de Windows asigna el `private` (`Friend` en Visual Basic) a los controles de contenedor como modificador de <xref:System.Windows.Forms.Panel>. Si la base de <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> tiene un control contenedor, no se aceptarán nuevos objetos secundarios en controles y formularios heredados. La solución es cambiar el modificador del control contenedor base para `protected` o `public`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Button>
- [Herencia visual de Windows Forms](windows-forms-visual-inheritance.md)
- [Tutorial: Demostración de la herencia Visual](walkthrough-demonstrating-visual-inheritance.md)
- [Cómo: Heredar Windows Forms](how-to-inherit-windows-forms.md)
