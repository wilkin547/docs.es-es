---
title: 'Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "77094480"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero

Las aplicaciones de WPF que se destinan a .NET Framework 4.7 y que se ejecutan en Windows a partir de Windows 10 Creators Update pueden habilitar la pila de lápiz/entada táctil de WPF basada en `WM_POINTER`.

## <a name="impact"></a>Impacto

Los desarrolladores que no habiliten explícitamente la compatibilidad del lápiz o la entrada táctil basados en puntero no deberían percibir ningún cambio en el comportamiento del lápiz o de la entrad táctil de WPF.

A continuación se muestran problemas conocidos actuales con la pila de lápiz o de entrada táctil basados en `WM_POINTER`:

- No se admiten las entradas manuscritas en tiempo real.

   A pesar de que los complementos de lápiz y entrada manuscrita siguen funcionando, se procesan en el subproceso de la interfaz de usuario, que puede provocar un rendimiento deficiente.

- El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.

  - La manipulación puede comportarse de manera diferente.

  - Arrastrar y colocar no mostrará la información adecuada para la entrada táctil. (Esto no afecta a la entrada de lápiz).

  - Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz/entrada táctil.

      Esto puede hacer que la aplicación deje de responder hasta que se detecte la entrada del mouse. En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a>Inclusión de la compatibilidad del lápiz o la entrada táctil basados en WM_POINTER

Los desarrolladores que quieran habilitar esta pila pueden agregar lo siguiente al archivo *app.config* de la aplicación.

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

Si se quita esta entrada o se establece su valor en `false`, se desactiva esta pila opcional.

## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
