---
title: 'Cómo: Agregar controles ActiveX a formularios Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2cedd71665dc098ca3a6a6bf43c74b2d3a11fe11
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Cómo: Agregar controles ActiveX a formularios Windows Forms
Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de formularios Windows Forms, también puede colocar controles ActiveX en formularios Windows Forms.  
  
> [!CAUTION]
>  Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.  
  
 Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas. Para obtener más información, consulte [componentes COM, cuadro de diálogo Personalizar cuadro de herramientas](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Para agregar un control ActiveX a su formulario Windows Forms  
  
-   Haga doble clic en el control en el cuadro de herramientas.  
  
     Visual Studio agrega todas las referencias al control en el proyecto. Para obtener más información sobre los aspectos que debe tener en cuenta al utilizar controles ActiveX en formularios Windows Forms, vea [consideraciones al alojar un ActiveX Control en un formulario Windows Forms](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente de lo esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX. Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera. Tenga en cuenta que este irregularidades evita que el código funciona con normalidad. Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Vea también  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
