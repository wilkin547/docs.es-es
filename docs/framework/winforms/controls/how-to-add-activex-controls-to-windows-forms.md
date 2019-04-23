---
title: Procedimiento para agregar controles ActiveX a formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166055"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedimiento para agregar controles ActiveX a formularios Windows Forms
Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.  
  
> [!CAUTION]
>  Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.  
  
 Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas. Para obtener más información, consulte [componentes COM, Personalizar cuadro de diálogo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Para agregar un control ActiveX a un formulario de Windows  
  
-   Haga doble clic en el control en el cuadro de herramientas.  
  
     Visual Studio agrega todas las referencias al control en el proyecto. Para obtener más información acerca de las cosas a tener en cuenta al usar controles ActiveX en Windows Forms, consulte [consideraciones al hospedar un ActiveX Control en un formulario de Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente del esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX. Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera. Tenga en cuenta que este irregularidad no evita que código funciona con normalidad. Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
