---
title: Información general sobre el componente HelpProvider
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
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738722"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Información general sobre el componente HelpProvider (Windows Forms)
El componente Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) se utiliza para asociar un archivo de ayuda HTML de ayuda 1. x (ya sea un archivo. chm, generado con el taller de ayuda HTML o un archivo. htm) con la aplicación Windows. Puede proporcionar ayuda de varias maneras:  
  
- Proporcionar ayuda contextual para los controles de Windows Forms.  
  
- Proporcionar ayuda contextual sobre un cuadro de diálogo concreto o controles específicos de un cuadro de diálogo.  
  
- Abra un archivo de ayuda en áreas específicas, como la Página principal de una tabla de contenido, el índice o una función de búsqueda.  
  
## <a name="using-the-help-provider"></a>Usar el proveedor de ayuda  
 Agregar un componente de <xref:System.Windows.Forms.HelpProvider> a Windows Forms permite que los demás controles del formulario expongan las propiedades de ayuda del componente <xref:System.Windows.Forms.HelpProvider>. Esto le permite proporcionar ayuda para los controles de Windows Forms. Puede asociar un archivo de ayuda al componente de <xref:System.Windows.Forms.HelpProvider> mediante la propiedad <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>. Especifique el tipo de ayuda que se proporciona llamando a <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> y proporcionando un valor de la enumeración <xref:System.Windows.Forms.HelpNavigator> para el control especificado. Proporcione la palabra clave o el tema para obtener ayuda llamando al método <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>.  
  
 Opcionalmente, para asociar una cadena de ayuda concreta a otro control, utilice el método <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>. La cadena que se asocia a un control mediante este método se muestra en una ventana emergente cuando el usuario presiona la tecla F1 mientras el control tiene el foco.  
  
 Si no se ha establecido <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>, debe utilizar <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para proporcionar el texto de ayuda. Si ha establecido <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> y la cadena de ayuda, la ayuda basada en <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> tendrá prioridad.  
  
> [!NOTE]
> Puede encontrar problemas al usar la ruta de acceso relativa al especificar la ruta de acceso al archivo de ayuda en el método <xref:System.Windows.Forms.Help.ShowHelp%2A> o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad del control <xref:System.Windows.Forms.HelpProvider>. Como tal, asegúrese de usar la ruta de acceso absoluta del archivo para especificar el archivo de ayuda.  
  
## <a name="see-also"></a>Vea también

- [Sistemas de ayuda en aplicaciones de Windows Forms](../advanced/help-systems-in-windows-forms-applications.md)
