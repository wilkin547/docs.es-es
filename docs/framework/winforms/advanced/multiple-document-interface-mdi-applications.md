---
title: Aplicaciones de interfaz de múltiples documentos (MDI)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956556"
---
# <a name="multiple-document-interface-mdi-applications"></a>Aplicaciones de interfaz de múltiples documentos (MDI)
Las aplicaciones de interfaz de múltiples documentos (MDI) le permiten mostrar varios documentos al mismo tiempo, con cada documento que se muestra en su propia ventana. Las aplicaciones MDI suelen tener un elemento de menú Ventana con submenús para cambiar entre ventanas o documentos.  
  
> [!NOTE]
> Hay algunas diferencias de comportamiento entre los formularios MDI y las ventanas de la interfaz de un único documento (SDI) en Windows Forms. La `Opacity` propiedad no afecta a la apariencia de los formularios MDI secundarios. Además, el <xref:System.Windows.Forms.Form.CenterToParent%2A> método no afecta al comportamiento de los formularios MDI secundarios.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimientos: Crear formularios MDI primarios](how-to-create-mdi-parent-forms.md)  
 Proporciona instrucciones para crear el contenedor para varios documentos dentro de una aplicación MDI.  
  
 [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)  
 Proporciona instrucciones para crear una o más ventanas que funcionan en un formulario primario MDI.  
  
 [Cómo: Determinar el elemento secundario MDI activo](how-to-determine-the-active-mdi-child.md)  
 Proporciona instrucciones para comprobar la ventana secundaria que tiene el foco (y enviar su contenido al portapapeles).  
  
 [Cómo: Enviar datos al elemento secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)  
 Proporciona instrucciones para transportar información a la ventana secundaria activa.  
  
 [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)  
 Proporciona instrucciones para colocar en mosaico, en cascada u organizar las ventanas secundarias de una aplicación MDI.
