---
title: Utilizar controles WPF
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
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8225447e6c0daa7894d622616131febb6ac82b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="using-wpf-controls"></a>Utilizar controles WPF
Puede usar controles de Windows Presentation Foundation (WPF) en las aplicaciones basadas en formularios Windows Forms. Aunque se trata de dos tecnologías de presentación diferentes, operan perfectamente entre sí.  
  
 El Diseñador de Windows Forms proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation. Un control WPF se hospeda un control de formularios Windows Forms especial que se denomina <xref:System.Windows.Forms.Integration.ElementHost>. Este control habilita el control WPF para participar en el diseño del formulario y recibir mensajes de teclado y mouse (ratón). En tiempo de diseño, puede organizar la <xref:System.Windows.Forms.Integration.ElementHost> controlar igual que lo haría con cualquier control de formularios Windows Forms.  
  
 También puede usar controles de formularios Windows Forms en las aplicaciones basadas en WPF. Para obtener más información, consulte [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## <a name="in-this-section"></a>En esta sección  
 [Copiar y pegar un control ElementHost en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Muestra cómo copiar un control de Windows Presentation Foundation en un formulario Windows Forms.  
  
 [Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo utilizar las características de diseño de formularios Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation.  
  
 [Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] para cambiar las propiedades de los controles WPF.  
  
 [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo crear un control de Windows Presentation Foundation para su uso en las aplicaciones basadas en formularios Windows Forms.  
  
 [Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Muestra cómo copiar un control de Windows Presentation Foundation de un formulario Windows Forms a otro.  
  
 [Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo seleccionar los tipos de control de Windows Presentation Foundation que desea mostrar en el formulario.  
  
 [Tutorial: Aplicar estilos al contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y la [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] para aplicar estilos a controles de Windows Presentation Foundation.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Describe una clase que puede utilizar para hospedar controles de Windows Presentation Foundation en las aplicaciones basadas en formularios Windows Forms.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Describe una clase que puede utilizar para hospedar controles de formularios Windows Forms en una aplicación basada en Windows Presentation Foundation.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Describe la interoperabilidad entre las tecnologías de Windows Presentation Foundation y Windows Forms.  
  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 Describe cómo diseñar controles de Windows Presentation Foundation en Visual Studio.
