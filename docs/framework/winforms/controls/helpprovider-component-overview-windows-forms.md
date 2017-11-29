---
title: "Información general sobre el componente HelpProvider (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42a788e44fde80662748e19a7244ce77bb26118f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="helpprovider-component-overview-windows-forms"></a>Información general sobre el componente HelpProvider (formularios Windows Forms)
Los formularios Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm, generado con HTML Help Workshop o un archivo .htm) con la aplicación de Windows. Puede proporcionar ayuda en una variedad de formas:  
  
-   Proporcionar ayuda contextual para los controles de formularios Windows Forms.  
  
-   Proporcionar ayuda contextual en un cuadro de diálogo determinado o controles específicos en un cuadro de diálogo.  
  
-   Abra un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, el índice o una función de búsqueda.  
  
## <a name="using-the-help-provider"></a>Mediante el proveedor de ayuda  
 Agregar un <xref:System.Windows.Forms.HelpProvider> componente al formulario Windows Forms permite a los demás controles en el formulario para exponer las propiedades de la Ayuda de la <xref:System.Windows.Forms.HelpProvider> componente. Esto le permite proporcionar ayuda para los controles del formulario Windows Forms. Puede asociar un archivo de ayuda con la <xref:System.Windows.Forms.HelpProvider> componente mediante el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad. Especificar el tipo de ayuda proporcionada mediante una llamada a <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> y proporcionar un valor comprendido entre el <xref:System.Windows.Forms.HelpNavigator> enumeración para el control especificado. Proporcionar la palabra clave o el tema de ayuda mediante una llamada a la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> método.  
  
 Si lo desea, para asociar una cadena de ayuda específica a otro control, use la <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> método. La cadena que se asocia a un control con este método se muestra en una ventana emergente cuando el usuario presiona la tecla F1 mientras el control tiene el foco.  
  
 Si <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> no se ha establecido, debe usar <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para proporcionar el texto de ayuda. Si ha establecido tanto <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> y la cadena de ayuda, Ayuda basada en <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> tendrá prioridad.  
  
> [!NOTE]
>  Puede encontrar problemas con la ruta de acceso relativa al especificando la ruta de acceso al archivo de ayuda en la <xref:System.Windows.Forms.Help.ShowHelp%2A> método o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad de la <xref:System.Windows.Forms.HelpProvider> control. Por lo tanto, asegúrese de usar la ruta de acceso absoluta del archivo para especificar el archivo de ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Sistemas de ayuda en aplicaciones de Windows Forms](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
