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
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500530"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualización de caracteres asiáticos con la propiedad ImeMode
El <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad se usa en formularios y controles para forzar un modo específico para un editor de métodos de entrada (IME). El IME es un componente esencial para escribir scripts en chino, japonés y coreano, ya que estos sistemas de escritura tienen más caracteres que pueden codificarse para un teclado normal. Por ejemplo, puede que solo quiera permitir caracteres ASCII en un cuadro de texto determinado. En tal caso puede establecer el <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad <xref:System.Windows.Forms.ImeMode> y los usuarios solo podrán escribir caracteres ASCII en ese cuadro de texto determinado. El valor predeterminado de la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad es <xref:System.Windows.Forms.ImeMode>, por lo que si establece la propiedad de un formulario, todos los controles del formulario heredarán dicha configuración. Para obtener más información, consulte <xref:System.Windows.Forms.Control.ImeMode%2A> ) y <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Vea también

- [Globalizar aplicaciones de Windows Forms](globalizing-windows-forms.md)
