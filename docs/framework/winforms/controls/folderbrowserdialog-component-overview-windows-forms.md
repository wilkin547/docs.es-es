---
title: Información general sobre el componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745729"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Información general del componente FolderBrowserDialog (formularios Windows Forms)

El componente <xref:System.Windows.Forms.FolderBrowserDialog> de Windows Forms es un cuadro de diálogo modal que se usa para examinar y seleccionar carpetas. También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.

> [!NOTE]
> Para seleccionar archivos, en lugar de carpetas, use el componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .

El componente de <xref:System.Windows.Forms.FolderBrowserDialog> se muestra en tiempo de ejecución mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>. Establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> para determinar la carpeta de nivel superior y todas las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo. Una vez que se muestra el cuadro de diálogo, puede usar la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> para obtener la ruta de acceso de la carpeta seleccionada.

Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.FolderBrowserDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
