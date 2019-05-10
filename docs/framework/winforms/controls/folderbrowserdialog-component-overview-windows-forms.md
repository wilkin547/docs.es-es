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
ms.openlocfilehash: cd89980ccad7e6c73094c1fb462d93cee8094959
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210401"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Información general del componente FolderBrowserDialog (formularios Windows Forms)

Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente es un cuadro de diálogo modal que se utiliza para examinar y seleccionar carpetas. También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.

> [!NOTE]
> Para seleccionar archivos, en lugar de carpetas, use el [OpenFileDialog](openfiledialog-component-windows-forms.md) componente.

El <xref:System.Windows.Forms.FolderBrowserDialog> componente se muestra en tiempo de ejecución mediante el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método. Establecer el <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad para determinar la carpeta de nivel superior y las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo. Una vez mostrado el cuadro de diálogo, se puede utilizar el <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad va a obtener la ruta de acceso de la carpeta que se ha seleccionado.

Cuando se agrega a un formulario, el <xref:System.Windows.Forms.FolderBrowserDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios de Windows](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog (componente)](folderbrowserdialog-component-windows-forms.md)
