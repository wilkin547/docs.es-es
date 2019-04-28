---
title: Información general sobre el componente OpenFileDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: ec275a5923d332d23205c79442fa23bc6e402e3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804564"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Información general sobre el componente OpenFileDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado. Es el mismo **abrir archivo** cuadro de diálogo expuesto por el sistema operativo Windows. Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="using-this-component"></a>Uso de este componente  
 Utilice este componente dentro de la aplicación basada en Windows como una solución sencilla para la selección de archivo en lugar de configurar su propio cuadro de diálogo. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.OpenFileDialog> componente, debe escribir su propia lógica de apertura de archivos.  
  
 Use el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Puede permitir a los usuarios seleccionados varios archivos que desea abrir con el <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> propiedad. Además, puede usar el <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> propiedad para determinar si aparece una casilla de solo lectura en el cuadro de diálogo. El <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> propiedad indica si está seleccionada la casilla de solo lectura. Por último, el <xref:System.Windows.Forms.FileDialog.Filter%2A> propiedad establece la cadena de filtro de nombre de archivo actual, que determina las opciones que aparecen en el cuadro "Archivos de tipo" en el cuadro de diálogo.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.OpenFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog (componente)](openfiledialog-component-windows-forms.md)
