---
title: Procedimiento para bloquear controles en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: ac5fbf33564ed2dd1a030132a35b36164f777519
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638572"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Procedimiento para bloquear controles en formularios Windows Forms
Al diseñar la interfaz de usuario (UI) de la aplicación de Windows, puede bloquear los controles una vez que se colocan correctamente, por lo que no accidentalmente mover o cambiar su tamaño al establecer otras propiedades.  
  
 Además, puede bloquear y desbloquear todos los controles del formulario a la vez, lo cual resulta útil para formularios con muchos controles, o puede desbloquear controles individuales. Una vez que haya colocado todos los controles donde desee en el formulario, bloquear en lugar de para evitar movimientos erróneos.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-lock-a-control"></a>Para bloquear un control  
  
1. En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `true`. (Haga doble clic en el nombre, se alterna el valor de propiedad).  
  
     Como alternativa, haga clic en el control y elija **Bloquear controles**.  
  
    > [!NOTE]
    >  Controles de bloqueo impide que se arrastran a un nuevo tamaño o la ubicación en la superficie de diseño. Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles por medio de la **propiedades** ventana o en el código.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>Para bloquear todos los controles en un formulario  
  
1. Desde el **formato** menú, elija **Bloquear controles**.  
  
    > [!NOTE]
    >  Este comando bloquea el tamaño del formulario, como el formulario es un control.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Para desbloquear todos los controles en un formulario bloqueados  
  
1. Desde el **formato** menú, elija **Bloquear controles**.  
  
     Todos los controles del formulario estaba bloqueados ahora están desbloqueada.  
  
### <a name="to-unlock-locked-controls-individually"></a>Para desbloquear individualmente los controles bloqueados  
  
1. En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `false`. (Haga doble clic en el nombre, se alterna el valor de propiedad).  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
