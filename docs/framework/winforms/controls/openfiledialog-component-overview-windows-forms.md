---
title: Información general sobre el componente OpenFileDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: a49298b2e2cc620ad95e2e0b601a2f49f6ff79d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536083"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Información general sobre el componente OpenFileDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado. Es el mismo **archivos abiertos** cuadro de diálogo expuesto por el sistema operativo Windows. Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="using-this-component"></a>Utilizando este componente  
 Utilice este componente dentro de la aplicación basada en Windows como una solución sencilla para seleccionar archivos, en lugar de configurar su propio cuadro de diálogo. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.OpenFileDialog> componente, debe escribir su propia lógica de apertura de archivos.  
  
 Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Puede permitir a los usuarios seleccionar varios archivos que desea abrir con el <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> propiedad. Además, puede usar el <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> propiedad para determinar si en el cuadro de diálogo aparece una casilla de solo lectura. El <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> propiedad indica si está seleccionada la casilla de verificación sólo lectura. Por último, el <xref:System.Windows.Forms.FileDialog.Filter%2A> propiedad establece la cadena de filtro de nombre de archivo actual, que determina las opciones que aparecen en el cuadro "Archivos de tipo" en el cuadro de diálogo.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.OpenFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog (componente)](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
