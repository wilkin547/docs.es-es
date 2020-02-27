---
title: Realizar tareas comunes con acciones de diseñador en controles
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634898"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a>Tutorial: realizar tareas comunes con las acciones del diseñador

A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente. En la lista siguiente se muestran algunas de las tareas que se realizan con frecuencia:

- Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.
- Acoplar un control a su elemento primario.
- Cambiar la orientación de un control de <xref:System.Windows.Forms.SplitContainer>.

Para agilizar el desarrollo, muchos controles ofrecen acciones de diseñador, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño. Estas tareas se denominan *verbos de acciones del diseñador*.

Las acciones del diseñador permanecen adjuntas a una instancia del control para su duración en el diseñador y siempre están disponibles.

## <a name="create-the-project"></a>Creación del proyecto

El primer paso es crear el proyecto y configurar el formulario.

1. En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **DesignerActionsExample**.

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="use-designer-actions"></a>Usar acciones del diseñador

Las acciones del diseñador siempre están disponibles en tiempo de diseño en los controles que las ofrecen.

1. Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario. Observe el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) que aparece a la derecha de la <xref:System.Windows.Forms.TabControl>.

2. Haga clic en el glifo de acciones del diseñador. En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** . Observe que se agrega una nueva página de pestañas a la <xref:System.Windows.Forms.TabControl>.

3. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

4. Haga clic en el glifo de acciones del diseñador. En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** . Observe que se agrega una nueva columna al control <xref:System.Windows.Forms.TableLayoutPanel>.

5. Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.

6. Haga clic en el glifo de acciones del diseñador. En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** . Observe que la barra divisora del control <xref:System.Windows.Forms.SplitContainer> ahora está orientada horizontalmente.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
