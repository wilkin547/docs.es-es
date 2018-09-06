---
title: 'Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: d1c69d2e9e89e0a4fed767216e8743a0ac9ac81d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891176"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms
Como construir formularios y controles para la aplicación de Windows Forms, hay muchas tareas que llevará a cabo varias veces. Estas son algunas de las tareas realizadas normalmente que encontrará:  
  
-   Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.  
  
-   Acoplar un control a su elemento primario.  
  
-   Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.  
  
 Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como éstas en un solo gesto en tiempo de diseño. Estas tareas se denominan *verbos de etiquetas inteligentes*.  
  
 Las etiquetas inteligentes permanecen adjuntas a una instancia del control de su duración en el diseñador y siempre están disponibles.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms  
  
-   Uso de etiquetas inteligentes  
  
-   Habilitación y deshabilitación de etiquetas inteligentes  
  
 Cuando termine, comprenderá el rol de estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample" (**archivo** > **New** > **proyecto**  >   **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).  
  
2.  Seleccione el formulario en el **Diseñador de Windows Forms**.  
  
## <a name="using-smart-tags"></a>Uso de etiquetas inteligentes  
 Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.  
  
#### <a name="to-use-smart-tags"></a>Utilizar etiquetas inteligentes  
  
1.  Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta su formulario. Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en la en paralelo de la <xref:System.Windows.Forms.TabControl>.  
  
2.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento. Observe que una nueva página de ficha se agrega a la <xref:System.Windows.Forms.TabControl>.  
  
3.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
4.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento. Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
5.  Arrastre un <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
6.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento. Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [Tutorial: Agregar etiquetas inteligentes a un componente de Windows Forms](https://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
