---
title: para controles de bloqueo
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736237"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Cómo: bloquear controles en Windows Forms

Al diseñar la interfaz de usuario (UI) de la aplicación Windows, puede bloquear los controles una vez que se colocan correctamente, de modo que no los mueva o cambie de tamaño accidentalmente al establecer otras propiedades.

Además, puede bloquear y desbloquear todos los controles del formulario a la vez, lo que resulta útil para los formularios con muchos controles o puede desbloquear controles individuales. Una vez que haya colocado todos los controles que desee en el formulario, bloquee todos en su lugar para evitar un movimiento erróneo.

## <a name="to-lock-a-control"></a>Para bloquear un control

En la ventana **propiedades** de Visual Studio, seleccione la propiedad **bloqueado** y, a continuación, seleccione **true**. (Si hace doble clic en el nombre, se alterna el valor de la propiedad).

También puede hacer clic con el botón secundario en el control y elegir **bloquear controles**.

> [!NOTE]
> Los controles de bloqueo evitan que se arrastren a un nuevo tamaño o ubicación en la superficie de diseño. Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles mediante la ventana **propiedades** o en el código.

## <a name="to-lock-all-the-controls-on-a-form"></a>Para bloquear todos los controles de un formulario

En el menú **formato** , elija **bloquear controles**.

> [!NOTE]
> Este comando bloquea también el tamaño del formulario, porque un formulario es un control.

## <a name="to-unlock-all-locked-controls-on-a-form"></a>Para desbloquear todos los controles bloqueados en un formulario

En el menú **formato** , elija **bloquear controles**.

Todos los controles previamente bloqueados en el formulario están ahora desbloqueados.

## <a name="to-unlock-locked-controls-individually"></a>Para desbloquear controles bloqueados individualmente

En la ventana **propiedades** , seleccione la propiedad **bloqueado** y, a continuación, seleccione **false**. (Si hace doble clic en el nombre, se alterna el valor de la propiedad).

## <a name="see-also"></a>Consulte también

- [Controles de Windows Forms](index.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
