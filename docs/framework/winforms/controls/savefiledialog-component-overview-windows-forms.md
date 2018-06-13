---
title: Información general sobre el componente SaveFileDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: be5f70e2e8b0d5143ef387819689ce95564a72d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537452"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Información general sobre el componente SaveFileDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.SaveFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado. Es el mismo que el estándar **Guardar archivo** cuadro de diálogo usado por Windows. Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="working-with-the-savefiledialog-component"></a>Trabajar con el componente SaveFileDialog  
 Utilícelo como una solución sencilla para permitir que los usuarios guarden archivos en lugar de configurar su propio cuadro de diálogo. Al basarse en cuadros de diálogo estándar de Windows, la funcionalidad básica de las aplicaciones que cree es resultará de inmediato familiar a los usuarios. Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.SaveFileDialog> componente, debe escribir su propia lógica de almacenamiento de archivos.  
  
 Puede usar el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Puede abrir un archivo en modo de lectura/escritura mediante el <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> método.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.SaveFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [SaveFileDialog (componente)](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
