---
title: Aplicaciones de interfaz de múltiples documentos (MDI)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61952053"
---
# <a name="multiple-document-interface-mdi-applications"></a>Aplicaciones de interfaz de múltiples documentos (MDI)
Las aplicaciones de interfaz de múltiples documentos (MDI) permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana. Las aplicaciones MDI suelen tengan un elemento de menú de ventana con submenús para cambiar entre ventanas o documentos.  
  
> [!NOTE]
>  Hay algunas diferencias de comportamiento entre formularios MDI y ventanas de la interfaz de único documento (SDI) en Windows Forms. El `Opacity` propiedad no afecta a la apariencia de formularios MDI secundarios. Además, el <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Crear formularios principales MDI](how-to-create-mdi-parent-forms.md)  
 Proporciona instrucciones para crear el contenedor para los diferentes documentos dentro de una aplicación MDI.  
  
 [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)  
 Proporciona instrucciones para crear una o varias ventanas que funcionen dentro de un formulario primario MDI.  
  
 [Cómo: Determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md)  
 Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido en el Portapapeles).  
  
 [Cómo: Enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)  
 Proporciona instrucciones para transportar información a la ventana secundaria activa.  
  
 [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)  
 Proporciona instrucciones para la colocación en mosaico, cascada u organizar las ventanas secundarias de una aplicación MDI.
