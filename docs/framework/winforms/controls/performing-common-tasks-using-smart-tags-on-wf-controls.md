---
title: 'Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a558f6d274f260fc91fd140e9dae2c740b1ae00d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537949"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms
Medida que genera los formularios y controles para la aplicación de formularios Windows Forms, hay muchas tareas que se realiza con frecuencia. Estas son algunas de las tareas realizadas normalmente que encontrará:  
  
-   Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.  
  
-   Acoplar un control a su elemento primario.  
  
-   Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.  
  
 Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes, como en una sola operación en tiempo de diseño. Estas tareas se denominan *verbos de etiqueta inteligente*.  
  
 Las etiquetas inteligentes permanecen conectadas a una instancia de control durante su duración en el diseñador y siempre están disponibles.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms  
  
-   Uso de etiquetas inteligentes  
  
-   Habilitar y deshabilitar las etiquetas inteligentes  
  
 Cuando termine, comprenderá el rol de estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample". Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el **Diseñador de Windows Forms**.  
  
## <a name="using-smart-tags"></a>Uso de etiquetas inteligentes  
 Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.  
  
#### <a name="to-use-smart-tags"></a>Utilizar etiquetas inteligentes  
  
1.  Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** al formulario. Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en paralelo de la <xref:System.Windows.Forms.TabControl>.  
  
2.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento. Observe que se agrega una nueva página de fichas a la <xref:System.Windows.Forms.TabControl>.  
  
3.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.  
  
4.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento. Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
5.  Arrastre un <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas** al formulario.  
  
6.  Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento. Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [Tutorial: Agregar etiquetas inteligentes a un componente de Windows Forms](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
