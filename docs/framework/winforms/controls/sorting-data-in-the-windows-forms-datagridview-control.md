---
title: Ordenar datos en el control DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742948"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Ordenar datos en el control DataGridView Windows Forms

De forma predeterminada, los usuarios pueden ordenar los datos de un control de <xref:System.Windows.Forms.DataGridView> haciendo clic en el encabezado de una columna de cuadro de texto (o presionando F3 cuando una celda de cuadro de texto se centra en .NET Framework 4.7.2 y versiones posteriores). Puede modificar la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode> de columnas específicas para permitir que los usuarios ordenen por otros tipos de columna cuando tenga sentido hacerlo. También puede ordenar los datos mediante programación por cualquier columna o por varias columnas.

## <a name="in-this-section"></a>En esta sección

[Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
Describe las opciones para ordenar los datos del control.

[Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
Describe cómo permitir a los usuarios ordenar por columnas que no se pueden ordenar de forma predeterminada.

[Personalizar la ordenación en el control DataGridView de formularios Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
Describe cómo ordenar los datos mediante programación y cómo personalizar la ordenación utilizando el evento <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> o implementando la interfaz <xref:System.Collections.IComparer>.

## <a name="reference"></a>Referencia

<xref:System.Windows.Forms.DataGridView>  
Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
Proporciona documentación de referencia para el método <xref:System.Windows.Forms.DataGridView.Sort%2A>.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
Proporciona documentación de referencia para la enumeración <xref:System.Windows.Forms.DataGridViewColumnSortMode>.

## <a name="see-also"></a>Vea también

- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
