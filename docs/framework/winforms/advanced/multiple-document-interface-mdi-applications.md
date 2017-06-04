---
title: "Aplicaciones de interfaz de m&#250;ltiples documentos (MDI) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "formularios, MDI"
  - "MDI"
  - "Windows Forms, MDI (aplicaciones)"
  - "ventanas, MDI"
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Aplicaciones de interfaz de m&#250;ltiples documentos (MDI)
Las aplicaciones MDI \(interfaz de múltiples documentos\) permiten mostrar varios documentos al mismo tiempo, cada uno de ellos en su propia ventana.  Las aplicaciones MDI suelen tener un elemento de menú Ventana con submenús que permiten cambiar entre ventanas o documentos.  
  
> [!NOTE]
>  Hay algunas diferencias de comportamiento entre los formularios MDI y las ventanas de interfaz de un solo documento \(SDI\) en formularios Windows Forms.  La propiedad `Opacity` no afecta a la apariencia de formularios MDI secundarios.  Además, el método <xref:System.Windows.Forms.Form.CenterToParent%2A> no afecta al comportamiento de los formularios MDI secundarios.  
  
## En esta sección  
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 Proporciona instrucciones para crear el contenedor para los diferentes documentos de una aplicación MDI.  
  
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 Proporciona instrucciones para crear una o más ventanas que funcionen dentro de un formulario MDI primario.  
  
 [Cómo: Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 Proporciona instrucciones para comprobar cuál es la ventana secundaria que tiene el foco \(y enviar su contenido al Portapapeles\).  
  
 [Cómo: Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 Proporciona instrucciones para transportar información a la ventana secundaria activa.  
  
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 Proporciona instrucciones para organizar las ventanas secundarias de una aplicación MDI, disponerlas en mosaico o disponerlas en cascada.