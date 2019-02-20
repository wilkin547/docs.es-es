---
title: Filtrar Agregar controles ActiveX a formularios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 52f914b1d6fe5d8a2707e1f4ab176036ebf62cf9
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441793"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Filtrar Agregar controles ActiveX a formularios de Windows
Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.  
  
> [!CAUTION]
>  Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.  
  
 Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas. Para obtener más información, consulte [componentes COM, Personalizar cuadro de diálogo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Para agregar un control ActiveX a un formulario de Windows  
  
-   Haga doble clic en el control en el cuadro de herramientas.  
  
     Visual Studio agrega todas las referencias al control en el proyecto. Para obtener más información acerca de las cosas a tener en cuenta al usar controles ActiveX en Windows Forms, consulte [consideraciones al hospedar un ActiveX Control en un formulario de Windows](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente del esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX. Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera. Tenga en cuenta que este irregularidad no evita que código funciona con normalidad. Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Vea también
- [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
