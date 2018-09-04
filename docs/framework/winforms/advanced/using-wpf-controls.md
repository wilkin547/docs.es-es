---
title: Utilizar controles WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 30b84f05898f823227415c410dc7ba5f89d58664
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504710"
---
# <a name="using-wpf-controls"></a>Utilizar controles WPF
Puede usar los controles de Windows Presentation Foundation (WPF) en sus aplicaciones basadas en Windows Forms. Aunque son dos tecnologías de vista diferente, interoperan fácilmente.  
  
 El Diseñador de Windows Forms proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation. Un control WPF se hospeda un control de Windows Forms especial que se denomina <xref:System.Windows.Forms.Integration.ElementHost>. Este control habilita el control WPF para participar en el diseño del formulario y recibir mensajes del teclado y mouse. En tiempo de diseño, puede organizar la <xref:System.Windows.Forms.Integration.ElementHost> controlar tal como lo haría con cualquier control de Windows Forms.  
  
 También puede usar controles de formularios Windows Forms en sus aplicaciones basadas en WPF. Para obtener más información, consulte [diseño XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).  
  
## <a name="in-this-section"></a>En esta sección  
 [Copiar y pegar un control ElementHost en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Se muestra cómo copiar un control de Windows Presentation Foundation en un formulario de Windows.  
  
 [Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Se muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation.  
  
 [Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] para cambiar las propiedades de controles de WPF.  
  
 [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Se muestra cómo crear un control de Windows Presentation Foundation para su uso en las aplicaciones basadas en Windows Forms.  
  
 [Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Se muestra cómo copiar un control de Windows Presentation Foundation de un formulario de Windows a otro.  
  
 [Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo seleccionar los tipos de control de Windows Presentation Foundation que desea mostrar en el formulario.  
  
 [Tutorial: Aplicar estilos al contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y la [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] para aplicar estilos a controles de Windows Presentation Foundation.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Describe una clase que puede utilizar para hospedar controles de Windows Presentation Foundation en sus aplicaciones basadas en Windows Forms.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Describe una clase que puede usar para hospedar controles de Windows Forms en su aplicación basada en Windows Presentation Foundation.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Describe la interoperabilidad entre las tecnologías de Windows Presentation Foundation y Windows Forms.  
  
 [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 Describe cómo diseñar controles de Windows Presentation Foundation en Visual Studio.
