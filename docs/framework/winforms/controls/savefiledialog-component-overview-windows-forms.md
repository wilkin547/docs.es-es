---
title: Información general sobre el componente SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743102"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Información general sobre el componente SaveFileDialog (formularios Windows Forms)

El componente <xref:System.Windows.Forms.SaveFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado. Es el mismo que el cuadro de diálogo **Guardar archivo** estándar utilizado por Windows. Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-savefiledialog-component"></a>Trabajar con el componente SaveFileDialog

Úselo como una solución sencilla para permitir que los usuarios guarden archivos en lugar de configurar su propio cuadro de diálogo. Al confiar en los cuadros de diálogo estándar de Windows, la funcionalidad básica de las aplicaciones que crea es inmediatamente familiar para los usuarios. No obstante, tenga en cuenta que al usar el componente de <xref:System.Windows.Forms.SaveFileDialog>, debe escribir su propia lógica de guardado de archivos.

Puede usar el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución. Puede abrir un archivo en modo de lectura y escritura mediante el método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.

Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.SaveFileDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog (componente)](savefiledialog-component-windows-forms.md)
