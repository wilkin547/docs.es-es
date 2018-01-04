---
title: "Información general sobre el componente FontDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9e3018d024254adb249860f7736399e7f2da72a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a>Información general sobre el componente FontDialog (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.FontDialog> componente es un cuadro de diálogo preconfigurado, que es el estándar de Windows **fuente** cuadro de diálogo que se utiliza para exponer las fuentes que están instaladas actualmente en el sistema. Utilícelo en la aplicación basada en Windows como una solución sencilla para la selección de fuente en lugar de configurar su propio cuadro de diálogo.  
  
 De forma predeterminada, el cuadro de diálogo muestra cuadros de lista para la fuente, estilo de fuente y tamaño; casillas de verificación para efectos como tachado y subrayado; una lista desplegable para Script. y un ejemplo de cómo aparecerá la fuente. (Script hace referencia a scripts de carácter distinto que están disponibles para una fuente determinada, por ejemplo, hebreo o japonés.) Para mostrar el cuadro de diálogo fuente, llame a la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
## <a name="key-properties"></a>Propiedades clave  
 El componente tiene un número de propiedades que configuran su apariencia. Las propiedades que establecen las selecciones del cuadro de diálogo son <xref:System.Windows.Forms.FontDialog.Font%2A> y <xref:System.Windows.Forms.FontDialog.Color%2A>. El <xref:System.Windows.Forms.FontDialog.Font%2A> propiedad establece la fuente, estilo, tamaño, script y efectos; por ejemplo, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog (componente)](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
