---
title: Procedimiento para enlazar un control de formularios Windows Forms a un tipo mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 5069d7d3b5ef4c5b05159dac521d32f5be8abdd1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046040"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Procedimiento para enlazar un control de formularios Windows Forms a un tipo mediante el diseñador

Al crear controles que interactúan con datos, a veces necesita enlazar un control a un tipo, en lugar de a un objeto. Normalmente necesita enlazar un control a un tipo en tiempo de diseño, cuando quizá no estén disponibles los datos, pero aún desea que los controles enlazados a datos muestren datos de una interfaz pública del tipo. Los procedimientos siguientes muestran cómo crear un nuevo <xref:System.Windows.Forms.BindingSource> que está enlazado a un tipo y, a continuación, cómo enlazar una de las propiedades del tipo a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad <xref:System.Windows.Forms.TextBox>de.

### <a name="to-bind-the-bindingsource-to-a-type"></a>Para enlazar BindingSource a un tipo

1. Crear un proyecto de Windows Forms **(archivo** > **nuevo** > **proyecto** >  **C# visual** o **Visual Basic** > **clásico** Desktop >   **Windows Forms aplicación**).

2. En la vista **diseño** , arrastre <xref:System.Windows.Forms.BindingSource> un componente al formulario.

3. En la ventana **propiedades** , haga clic en la flecha <xref:System.Windows.Forms.BindingSource.DataSource%2A> de la propiedad.

4. En el **Editor de tipos de la interfaz de usuario de orígenes de datos**, haga clic en **Agregar origen de datos del proyecto**.

5. En la página **Elegir un tipo de origen de datos**, seleccione **Objeto** y haga clic en **Siguiente**.

6. Seleccione el tipo al que desea enlazarlo:

    - Si el tipo al que desea enlazarlo se encuentra en el proyecto actual o el ensamblado que contiene el tipo ya se ha agregado como una referencia, expanda los nodos para encontrar el tipo que desee y a continuación selecciónelo.

      O bien

    - Si el tipo al que desea enlazarlo se encuentra en otro ensamblado, no actualmente en la lista de referencias, haga clic en **Agregar referencia** y después haga clic en la pestaña **Proyectos**. Seleccione el proyecto que contiene el objeto comercial que desea y haga clic en **Aceptar**. Este proyecto aparecerá en la lista de ensamblados, por lo que puede expandir los nodos para encontrar el tipo desee y, a continuación, seleccionarlo.

      > [!NOTE]
      > Si desea enlazar a un tipo de un marco o un ensamblado de Microsoft, desactive la casilla **Ocultar los ensamblados que empiecen por Microsoft o sistema**.

7. Haga clic en **Siguiente** y después haga clic en **Finalizar**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>Para enlazar el control a BindingSource

1. Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.

2. En la ventana **Propiedades**, expanda el nodo **(DataBindings)** .

3. Haga clic en la flecha situada <xref:System.Windows.Forms.TextBox.Text%2A> junto a la propiedad.

4. En el **Editor de tipos de interfaz de usuario de DataSource**, <xref:System.Windows.Forms.BindingSource> expanda el nodo del agregado anteriormente y seleccione la propiedad del tipo enlazado que desea <xref:System.Windows.Forms.TextBox.Text%2A> enlazar a <xref:System.Windows.Forms.TextBox>la propiedad de.

## <a name="see-also"></a>Vea también

- [Componente BindingSource](bindingsource-component.md)
- [Cómo: Enlazar un control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
