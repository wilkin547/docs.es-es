---
title: Procedimiento para agregar controles ActiveX a formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987062"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedimiento para agregar controles ActiveX a formularios Windows Forms

Aunque el Diseñador de Windows Forms de Visual Studio está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.

> [!CAUTION]
> Existen limitaciones de rendimiento para Windows Forms cuando se agregan controles ActiveX a ellos.

Antes de agregar controles ActiveX al formulario, debe agregarlos al cuadro de herramientas. Para obtener más información, vea [componentes com, cuadro de diálogo Personalizar cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).

## <a name="add-an-activex-control-to-your-windows-form"></a>Agregar un control ActiveX a Windows Forms

Para agregar un control ActiveX a Windows Forms, haga doble clic en el control en el cuadro de herramientas.

Visual Studio agrega todas las referencias al control en el proyecto. Para obtener más información sobre los aspectos que se deben tener en cuenta al utilizar controles ActiveX en Windows Forms, vea [consideraciones al hospedar un control ActiveX en Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> El Windows Forms importador de controles ActiveX (AxImp. exe) crea argumentos de evento de un tipo diferente del esperado al importar las bibliotecas de vínculos dinámicos de ActiveX. Los argumentos creados por Aximp. exe son similares a los siguientes: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera. Tenga en cuenta que esta irregularidad no impide que el código funcione con normalidad. Para obtener más información, vea Windows Forms el importador de [controles ActiveX (Aximp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
