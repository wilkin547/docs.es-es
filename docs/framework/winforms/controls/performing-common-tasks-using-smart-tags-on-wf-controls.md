---
title: 'Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015765"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Tutorial: Realizar tareas comunes con etiquetas inteligentes

A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente. Estas son algunas de las tareas que se realizan con frecuencia:

- Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.

- Acoplar un control a su elemento primario.

- Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.

Para agilizar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño. Estas tareas se denominan *verbos de etiqueta inteligente*.

Las etiquetas inteligentes permanecen adjuntas a una instancia de control para su duración en el diseñador y siempre están disponibles.

## <a name="create-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto y configurar el formulario.

1. En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **SmartTagsExample**.

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="use-smart-tags"></a>Usar etiquetas inteligentes

Las etiquetas inteligentes siempre están disponibles en tiempo de diseño en los controles que las ofrecen.

1. Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario. Observe el glifo de etiqueta inteligente (![glifo](./media/vs-winformsmttagglyph.gif)de etiqueta inteligente) que aparece <xref:System.Windows.Forms.TabControl>en el lado de.

2. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** . Observe que se agrega una nueva página de pestañas <xref:System.Windows.Forms.TabControl>a.

3. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

4. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** . Observe que se agrega una nueva columna al <xref:System.Windows.Forms.TableLayoutPanel> control.

5. Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.

6. Haga clic en el glifo de etiqueta inteligente. En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** . Observe que la <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientada horizontalmente.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
