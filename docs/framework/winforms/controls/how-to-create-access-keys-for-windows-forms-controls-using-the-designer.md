---
title: Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 410fc0134046c5fa7e05bfcd38ce6818244a0a54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307878"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón. Permite al usuario "haga clic en" un botón presionando la tecla ALT en combinación con la clave de acceso predefinidas. Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por lo tanto, su `Text` propiedad se establece en "Imprimir" Agregar una y comercial (&) delante de la letra "P" hace que la letra "P" estar subrayados en el texto del botón en tiempo de ejecución. El usuario puede ejecutar el comando asociado con el botón presionando ALT + P. No puede tener una clave de acceso para un control que no se puede recibir el foco.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Para crear una clave de acceso para un control  
  
1. En el **propiedades** ventana, establezca el `Text` en una cadena que incluye una y comercial (&) delante de la letra que será la clave de acceso de propiedad. Por ejemplo, para establecer la letra "P" como la clave de acceso, escriba **& impresión** en la cuadrícula.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Button>
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Establecer el texto mostrado por un Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
