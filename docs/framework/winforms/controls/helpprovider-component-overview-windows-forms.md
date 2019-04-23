---
title: Información general sobre el componente HelpProvider (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 177b61cab99d21a844298632020244fa424d8d2a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176584"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Información general sobre el componente HelpProvider (formularios Windows Forms)
Los formularios de Windows [HelpProvider](helpprovider-component-windows-forms.md) componente se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm generado con HTML Help Workshop o un archivo .htm) con la aplicación de Windows. Puede proporcionar ayuda en una variedad de formas:  
  
-   Proporcionar ayuda contextual para los controles de Windows Forms.  
  
-   Proporcionar ayuda contextual en un cuadro de diálogo determinado o controles específicos en un cuadro de diálogo.  
  
-   Abra un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, el índice o una función de búsqueda.  
  
## <a name="using-the-help-provider"></a>Mediante el proveedor de ayuda  
 Agregar un <xref:System.Windows.Forms.HelpProvider> componente al formulario Windows permite que los demás controles en el formulario para exponer las propiedades de la Ayuda de la <xref:System.Windows.Forms.HelpProvider> componente. Esto le permite proporcionar ayuda para los controles en el formulario de Windows. Puede asociar un archivo de ayuda con la <xref:System.Windows.Forms.HelpProvider> componente mediante el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad. Especifique el tipo de ayuda que se proporciona mediante una llamada a <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> y proporcione un valor de la <xref:System.Windows.Forms.HelpNavigator> enumeración para el control especificado. Proporcionar la palabra clave o el tema de ayuda mediante una llamada a la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> método.  
  
 Si lo desea, para asociar una cadena de ayuda específica a otro control, use el <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> método. La cadena que se asocia a un control con este método se muestra en una ventana emergente cuando el usuario presiona la tecla F1 mientras el control tiene el foco.  
  
 Si <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> no se ha establecido, debe usar <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para proporcionar el texto de ayuda. Si ha establecido tanto <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> y la cadena de ayuda, ayuda según <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> tendrá prioridad.  
  
> [!NOTE]
>  Puede encontrar problemas con la ruta de acceso relativa al especificar la ruta de acceso al archivo de ayuda en la <xref:System.Windows.Forms.Help.ShowHelp%2A> método o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad de la <xref:System.Windows.Forms.HelpProvider> control. Por lo tanto, asegúrese de usar la ruta de acceso absoluta del archivo para especificar el archivo de ayuda.  
  
## <a name="see-also"></a>Vea también

- [Sistemas de ayuda en aplicaciones de Windows Forms](../advanced/help-systems-in-windows-forms-applications.md)
