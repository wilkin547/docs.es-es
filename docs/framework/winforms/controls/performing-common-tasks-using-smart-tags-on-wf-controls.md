---
title: 'Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211419"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms

Como construir formularios y controles para la aplicación de Windows Forms, hay muchas tareas que llevará a cabo varias veces. Estas son algunas de las tareas realizadas normalmente que encontrará:

- Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.

- Acoplar un control a su elemento primario.

- Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.

Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como éstas en un solo gesto en tiempo de diseño. Estas tareas se denominan *verbos de etiquetas inteligentes*.

Las etiquetas inteligentes permanecen adjuntas a una instancia del control de su duración en el diseñador y siempre están disponibles.

Las tareas ilustradas en este tutorial incluyen:

- Crear un proyecto de Windows Forms

- Uso de etiquetas inteligentes

- Habilitación y deshabilitación de etiquetas inteligentes

Cuando termine, comprenderá el rol de estas importantes características de diseño.

## <a name="create-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto y configurar el formulario.

1. En Visual Studio, cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample" (**archivo** > **New** > **proyecto**  >  **Visual C#**  o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="use-smart-tags"></a>Utilizar etiquetas inteligentes

Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.

1. Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta su formulario. Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en la en paralelo de la <xref:System.Windows.Forms.TabControl>.

2. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento. Observe que una nueva página de ficha se agrega a la <xref:System.Windows.Forms.TabControl>.

3. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

4. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento. Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.

5. Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.

6. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento. Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [Tutorial: Incorporación de etiquetas inteligentes a un componente de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))
