---
title: Visualización de caracteres asiáticos con la propiedad ImeMode
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: d3733f642d4218c851040582ee5637b5486a7804
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208633"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualización de caracteres asiáticos con la propiedad ImeMode
El <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad se usa en los formularios y controles para imponer un modo determinado a un editor de métodos de entrada (IME). El IME es un componente esencial para escribir scripts en chino, japonés y coreano, ya que estos sistemas de escritura tienen más caracteres que pueden codificarse para un teclado normal. Por ejemplo, puede que solo quiera permitir caracteres ASCII en un cuadro de texto determinado. En tal caso puede establecer la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad <xref:System.Windows.Forms.ImeMode> y los usuarios sólo podrán escribir caracteres ASCII para ese cuadro de texto determinado. El valor predeterminado de la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad es <xref:System.Windows.Forms.ImeMode>, por lo que si establece la propiedad de un formulario, todos los controles del formulario heredarán esa configuración. Para obtener más información, consulte <xref:System.Windows.Forms.Control.ImeMode%2A> ) y <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Vea también

[Globalizar aplicaciones de Windows Forms](globalizing-windows-forms.md)
