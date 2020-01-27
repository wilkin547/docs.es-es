---
title: Información general sobre el componente FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745706"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Información general sobre el componente FontDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.FontDialog> de Windows Forms es un cuadro de diálogo configurado previamente, que es el cuadro de diálogo **fuente** estándar de Windows que se usa para exponer las fuentes que están instaladas actualmente en el sistema. Úselo en su aplicación basada en Windows como una solución sencilla para la selección de fuentes en lugar de configurar su propio cuadro de diálogo.  
  
 De forma predeterminada, el cuadro de diálogo muestra los cuadros de lista de fuente, estilo de fuente y tamaño; casillas de efectos como tachado y subrayado; lista desplegable para script; y un ejemplo de cómo aparecerá la fuente. (El script hace referencia a distintos scripts de caracteres que están disponibles para una fuente determinada, por ejemplo, hebreo o japonés). Para mostrar el cuadro de diálogo fuente, llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="key-properties"></a>Propiedades clave  
 El componente tiene varias propiedades que configuran su apariencia. Las propiedades que establecen las selecciones de cuadro de diálogo son <xref:System.Windows.Forms.FontDialog.Font%2A> y <xref:System.Windows.Forms.FontDialog.Color%2A>. La propiedad <xref:System.Windows.Forms.FontDialog.Font%2A> establece la fuente, el estilo, el tamaño, el script y los efectos; por ejemplo, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog (componente)](fontdialog-component-windows-forms.md)
