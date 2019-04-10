---
title: Filtrar para crear formularios principales MDI
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 120a7d45e01b0460f0c5e50896f58d026c4c3b9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216319"
---
# <a name="how-to-create-mdi-parent-forms"></a>Filtrar para crear formularios principales MDI
> [!IMPORTANT]
>  En este tema se usa el control <xref:System.Windows.Forms.MainMenu>, que se ha reemplazado por el control <xref:System.Windows.Forms.MenuStrip>. El control <xref:System.Windows.Forms.MainMenu> se conserva por razones de compatibilidad con versiones anteriores y uso en el futuro, si así lo decide.  Para obtener información acerca de cómo crear una MDI formulario primario mediante el uso de un <xref:System.Windows.Forms.MenuStrip>, vea [Cómo: Crear una lista de ventanas MDI con MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 La base de una aplicación de interfaz de múltiples documentos (MDI) es el formulario primario MDI. Se trata del formulario que contiene las ventanas secundarias de MDI, que son las subventanas donde el usuario interactúa con la aplicación MDI. Crear un formulario primario MDI es fácil, tanto en el Diseñador de Windows Forms como mediante programación.  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a>Para crear un formulario primario MDI en tiempo de diseño  
  
1.  Cree un proyecto de aplicación para Windows.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad **true**.  
  
     Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.  
  
    > [!NOTE]
    >  Mientras configura las propiedades en la ventana **Propiedades**, también puede establecer la propiedad `WindowState` en **Maximizado**, si lo desea, ya que esto facilita la manipulación de las ventanas secundarias de MDI cuando el formulario primario está maximizado. Además, tenga en cuenta que el borde del formulario primario MDI seleccionará el color del sistema (definido en el Panel de Control del sistema Windows), y no el color de fondo que haya establecido en la propiedad <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.  
  
3.  En el **Cuadro de herramientas**, arrastre un control **MenuStrip** al formulario. Cree un elemento de menú de nivel superior con la propiedad **Text** establecida en **&Archivo** con los elementos de submenú **&Nuevo** y **&Cerrar**. Cree también un elemento de menú de nivel superior **&Ventana**.  
  
     El primer menú creará y ocultará los elementos de menú en tiempo de ejecución, mientras que el segundo realizará un seguimiento de las ventanas secundarias de MDI abiertas. Llegado este punto, habrá creado una ventana primaria de MDI.  
  
4.  Presione **F5** para ejecutar la aplicación. Para obtener información sobre cómo crear ventanas secundarias MDI que funcionen dentro del formulario primario MDI, consulte [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md)
- [Filtrar para crear formularios secundarios MDI](how-to-create-mdi-child-forms.md)
- [Filtrar para determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md)
- [Filtrar para enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)
- [Filtrar para organizar formularios secundarios MDI](how-to-arrange-mdi-child-forms.md)
