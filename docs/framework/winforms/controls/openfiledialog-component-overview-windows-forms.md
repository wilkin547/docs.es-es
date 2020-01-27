---
title: Información general sobre el componente OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728438"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Información general sobre el componente OpenFileDialog (formularios Windows Forms)

El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado. Es el mismo cuadro de diálogo **Abrir archivo** expuesto por el sistema operativo Windows. Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.

## <a name="use-this-component"></a>Usar este componente

Use este componente en su aplicación basada en Windows como una solución sencilla para la selección de archivos en lugar de configurar su propio cuadro de diálogo. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. No obstante, tenga en cuenta que al usar el componente de <xref:System.Windows.Forms.OpenFileDialog>, debe escribir su propia lógica de apertura de archivos.

Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución. Puede permitir que los usuarios seleccionen varios archivos para que se abran con la propiedad <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>. Además, puede utilizar la propiedad <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> para determinar si aparece una casilla de solo lectura en el cuadro de diálogo. La propiedad <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> indica si la casilla de solo lectura está activada. Por último, la propiedad <xref:System.Windows.Forms.FileDialog.Filter%2A> establece la cadena actual de filtro de nombres de archivo, que determina las opciones que aparecen en el cuadro "archivos de tipo" del cuadro de diálogo.

Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.OpenFileDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
