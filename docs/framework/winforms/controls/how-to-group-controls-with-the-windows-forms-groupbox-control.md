---
title: "Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d29de04b4e221105bb02e58de01344f13af69f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms
Formularios Windows Forms <xref:System.Windows.Forms.GroupBox> controles se utilizan para agrupar otros controles. Hay tres razones para los controles de grupo:  
  
-   Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.  
  
-   Para crear la agrupación de programación (de botones de radio, por ejemplo).  
  
-   Para mover los controles como una unidad en tiempo de diseño.  
  
### <a name="to-create-a-group-of-controls"></a>Para crear un grupo de controles  
  
1.  Dibujar un <xref:System.Windows.Forms.GroupBox> control en un formulario.  
  
2.  Agregar otros controles al cuadro de grupo, cada uno de ellos dentro del cuadro de grupo de dibujo.  
  
     Si dispone de los controles existentes que desee incluir en un cuadro de grupo, puede seleccionar todos los controles, como cortar a ellos en el Portapapeles, seleccione la <xref:System.Windows.Forms.GroupBox> de control y, a continuación, pegarlos en el cuadro de grupo. También puede arrastrar en el cuadro de grupo.  
  
3.  Establecer el <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo para un título apropiado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.GroupBox>  
 [GroupBox (control)](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
