---
title: Aplicaciones de interfaz de múltiples documentos (MDI)
description: Obtenga información sobre cómo Windows Forms las aplicaciones de interfaz de múltiples documentos (MDI) le permiten mostrar varios documentos al mismo tiempo, y cada documento se muestra en su propia ventana.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174658"
---
# <a name="multiple-document-interface-mdi-applications"></a>Aplicaciones de interfaz de múltiples documentos (MDI)
Las aplicaciones de interfaz de múltiples documentos (MDI) le permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana. Las aplicaciones MDI suelen tener un elemento de menú Ventana con submenús para cambiar entre ventanas o documentos.  
  
> [!NOTE]
> Hay algunas diferencias de comportamiento entre los formularios MDI y las ventanas de la interfaz de un único documento (SDI) en Windows Forms. La `Opacity` propiedad no afecta a la apariencia de los formularios MDI secundarios. Además, el <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimiento para crear formularios principales MDI](how-to-create-mdi-parent-forms.md)  
 Proporciona instrucciones para crear el contenedor para varios documentos dentro de una aplicación MDI.  
  
 [Procedimiento para crear formularios secundarios MDI](how-to-create-mdi-child-forms.md)  
 Proporciona instrucciones para crear una o más ventanas que funcionan en un formulario primario MDI.  
  
 [Procedimiento para determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md)  
 Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido al portapapeles).  
  
 [Procedimiento para enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)  
 Proporciona instrucciones para transportar información a la ventana secundaria activa.  
  
 [Procedimiento para organizar formularios secundarios MDI](how-to-arrange-mdi-child-forms.md)  
 Proporciona instrucciones para colocar en mosaico, en cascada u organizar las ventanas secundarias de una aplicación MDI.
