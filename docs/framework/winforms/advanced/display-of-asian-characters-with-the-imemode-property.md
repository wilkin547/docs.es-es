---
title: "Visualización de caracteres asiáticos con la propiedad ImeMode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971fd9a75f936d2ec63eea6a086c681ec996652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualización de caracteres asiáticos con la propiedad ImeMode
El <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad se usa en los formularios y controles para imponer un modo determinado a un editor de métodos de entrada (IME). El IME es un componente esencial para escribir scripts en chino, japonés y coreano, ya que estos sistemas de escritura tienen más caracteres que pueden codificarse para un teclado normal. Por ejemplo, puede que solo quiera permitir caracteres ASCII en un cuadro de texto determinado. En tal caso puede establecer la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad <xref:System.Windows.Forms.ImeMode> y los usuarios sólo podrán escribir caracteres ASCII para ese cuadro de texto determinado. El valor predeterminado de la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad es <xref:System.Windows.Forms.ImeMode>, por lo que si establece la propiedad de un formulario, todos los controles del formulario heredarán esa configuración. Para obtener más información, consulte <xref:System.Windows.Forms.Control.ImeMode%2A> ) y <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Vea también  
 [Globalizar Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
