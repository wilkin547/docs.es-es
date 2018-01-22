---
title: "Cómo: Bloquear controles en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f5cd70e71a4a8bc48a3240055117dadc1086a50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Cómo: Bloquear controles en formularios Windows Forms
Al diseñar la interfaz de usuario (UI) de la aplicación de Windows, puede bloquear los controles, una vez ubicados correctamente, por lo que no accidentalmente mover o cambiar su tamaño al establecer otras propiedades.  
  
 Además, puede bloquear y desbloquear todos los controles del formulario al mismo tiempo, lo cual es útil para formularios con muchos controles, o puede desbloquear controles individuales. Una vez que haya colocado todos los controles donde desee en el formulario, bloquéelos todos en contexto para evitar movimientos erróneos.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-lock-a-control"></a>Para bloquear un control  
  
1.  En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `true`. (Haga doble clic en el nombre cambia el valor de propiedad.)  
  
     O bien, haga clic en el control y elija **Bloquear controles**.  
  
    > [!NOTE]
    >  Controles de bloqueo les impide que se está arrastrando a un nuevo tamaño o la ubicación en la superficie de diseño. Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles por medio de la **propiedades** ventana o en el código.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>Para bloquear todos los controles en un formulario  
  
1.  Desde el **formato** menú, elija **Bloquear controles**.  
  
    > [!NOTE]
    >  Este comando bloquea el tamaño del formulario, puesto que un formulario es un control.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Para desbloquear todos los controles en un formulario bloqueados  
  
1.  Desde el **formato** menú, elija **Bloquear controles**.  
  
     Todos los controles que estaba bloqueados en el formulario ahora están desbloqueados.  
  
### <a name="to-unlock-locked-controls-individually"></a>Para desbloquear individualmente los controles bloqueados  
  
1.  En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `false`. (Haga doble clic en el nombre cambia el valor de propiedad.)  
  
## <a name="see-also"></a>Vea también  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
