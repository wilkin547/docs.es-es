---
title: Procedimiento Crear formularios principales MDI
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 1cc3d813b77ddf8220242f4a1dfc7fe39f9cb520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512572"
---
# <a name="how-to-create-mdi-parent-forms"></a>Procedimiento Crear formularios principales MDI
> [!IMPORTANT]
>  En este tema se usa el control <xref:System.Windows.Forms.MainMenu>, que se ha reemplazado por el control <xref:System.Windows.Forms.MenuStrip>. El control <xref:System.Windows.Forms.MainMenu> se conserva por razones de compatibilidad con versiones anteriores y uso en el futuro, si así lo decide.  Para obtener información acerca de cómo crear una MDI formulario primario mediante el uso de un <xref:System.Windows.Forms.MenuStrip>, vea [Cómo: Crear una lista de ventanas MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 La base de una aplicación de interfaz de múltiples documentos (MDI) es el formulario primario MDI. Se trata del formulario que contiene las ventanas secundarias de MDI, que son las subventanas donde el usuario interactúa con la aplicación MDI. Crear un formulario primario MDI es fácil, tanto en el Diseñador de Windows Forms como mediante programación.  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a>Para crear un formulario primario MDI en tiempo de diseño  
  
1.  Cree un proyecto de aplicación para Windows.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad **true**.  
  
     Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.  
  
    > [!NOTE]
    >  Mientras configura las propiedades en la ventana **Propiedades**, también puede establecer la propiedad `WindowState` en **Maximizado**, si lo desea, ya que esto facilita la manipulación de las ventanas secundarias de MDI cuando el formulario primario está maximizado. Además, tenga en cuenta que el borde del formulario primario MDI seleccionará el color del sistema (definido en el Panel de Control del sistema Windows), y no el color de fondo que haya establecido en la propiedad <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.  
  
3.  En el **Cuadro de herramientas**, arrastre un control **MenuStrip** al formulario. Cree un elemento de menú de nivel superior con la propiedad **Text** establecida en **&Archivo** con los elementos de submenú **&Nuevo** y **&Cerrar**. Cree también un elemento de menú de nivel superior **&Ventana**.  
  
     El primer menú creará y ocultará los elementos de menú en tiempo de ejecución, mientras que el segundo realizará un seguimiento de las ventanas secundarias de MDI abiertas. Llegado este punto, habrá creado una ventana primaria de MDI.  
  
4.  Presione **F5** para ejecutar la aplicación. Para obtener información sobre cómo crear ventanas secundarias MDI que funcionen dentro del formulario primario MDI, consulte [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).  
  
## <a name="see-also"></a>Vea también
- [Aplicaciones de interfaz de múltiples documentos (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [Cómo: Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [Cómo: Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
- [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
