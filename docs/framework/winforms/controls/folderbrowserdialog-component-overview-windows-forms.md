---
title: Información general del componente FolderBrowserDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: ce449937b89c686c868dcf337f46f1816d08d191
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717667"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Información general del componente FolderBrowserDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente es un cuadro de diálogo modal que se utiliza para examinar y seleccionar carpetas. También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.  
  
> [!NOTE]
>  Para seleccionar archivos, en lugar de carpetas, use el [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) componente.  
  
 El <xref:System.Windows.Forms.FolderBrowserDialog> componente se muestra en tiempo de ejecución mediante el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método. Establecer el <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad para determinar la carpeta de nivel superior y las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo. Una vez mostrado el cuadro de diálogo, se puede utilizar el <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad va a obtener la ruta de acceso de la carpeta que se ha seleccionado.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.FolderBrowserDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog (componente)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
