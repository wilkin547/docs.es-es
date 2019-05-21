---
title: Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: 37ab3823a41cca2eeea550c90e92e90bc364c759
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960350"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms mediante el diseñador

Controles de formularios Windows Forms normalmente muestran algún texto relacionado con la función principal del control. Por ejemplo, un <xref:System.Windows.Forms.Button> control normalmente muestra un título que indica qué acción se realizará cuando se hace clic en el botón. Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>. Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.

### <a name="to-set-the-text-and-font-with-the-designer"></a>Para establecer el texto y la fuente con el diseñador

1. En la ventana Propiedades, establezca el <xref:System.Windows.Forms.Control.Text%2A> propiedad del control en una cadena adecuada.

     Para crear una tecla de método abreviado subrayada, incluya una y comercial (&) delante de la letra que será la tecla de método abreviado.

2. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la <xref:System.Windows.Forms.Control.Font%2A> propiedad.

     En el cuadro de diálogo Fuente estándar, seleccione la fuente, estilo de fuente, tamaño, efectos (por ejemplo, tachado o subrayado) y secuencias de comandos que desee.

## <a name="see-also"></a>Vea también

- [Cómo: Establecer el texto mostrado por un Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Utilizar fuentes y texto](../advanced/using-fonts-and-text.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
