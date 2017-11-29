---
title: "Aplicaciones de interfaz de múltiples documentos (MDI)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c122931b0a00f487ddab07550913988462cfd50e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="multiple-document-interface-mdi-applications"></a>Aplicaciones de interfaz de múltiples documentos (MDI)
Aplicaciones de interfaz de múltiples documentos (MDI) permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana. Las aplicaciones MDI suelen tengan un elemento de menú Ventana con submenús que permiten cambiar entre ventanas o documentos.  
  
> [!NOTE]
>  Hay algunas diferencias de comportamiento entre formularios MDI y ventanas de la interfaz de único documento (SDI) en formularios Windows Forms. El `Opacity` propiedad no afecta a la apariencia de formularios MDI secundarios. Además, la <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 Proporciona instrucciones para crear el contenedor para los distintos documentos dentro de una aplicación MDI.  
  
 [Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 Proporciona instrucciones para crear una o varias ventanas que se ejecutan dentro de un formulario primario MDI.  
  
 [Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido en el Portapapeles).  
  
 [Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 Proporciona instrucciones para transportar la información de la ventana secundaria activa.  
  
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 Proporciona instrucciones para la disposición en mosaico, en cascada y organizar las ventanas secundarias de una aplicación MDI.
