---
title: Procedimiento para agregar controles ActiveX a formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210388"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedimiento para agregar controles ActiveX a formularios Windows Forms

Aunque el Diseñador de Windows Forms en Visual Studio está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.

> [!CAUTION]
> Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.

Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas. Para obtener más información, consulte [componentes COM, Personalizar cuadro de diálogo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).

## <a name="add-an-activex-control-to-your-windows-form"></a>Agregue un control ActiveX a un formulario de Windows

Para agregar un control ActiveX a un formulario de Windows, haga doble clic en el control en el cuadro de herramientas.

Visual Studio agrega todas las referencias al control en el proyecto. Para obtener más información acerca de las cosas a tener en cuenta al usar controles ActiveX en Windows Forms, consulte [consideraciones al hospedar un ActiveX Control en un formulario de Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente del esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX. Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera. Tenga en cuenta que este irregularidad no evita que código funciona con normalidad. Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
