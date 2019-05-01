---
title: Información general sobre el componente ImageList (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: 9869e647613ccf009954a5d65445947fbced40e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971176"
---
# <a name="imagelist-component-overview-windows-forms"></a>Información general sobre el componente ImageList (formularios Windows Forms)

El componente <xref:System.Windows.Forms.ImageList> de Windows Forms se usa para almacenar imágenes que posteriormente se pueden mostrar en los controles. Una lista de imágenes permite escribir código para un catálogo único y coherente de imágenes. Por ejemplo, puede girar las imágenes mostradas por un control <xref:System.Windows.Forms.Button> cambiando la propiedad <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> o <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> del botón. También puede asociar la misma lista de imágenes con varios controles. Por ejemplo, si está usando un control <xref:System.Windows.Forms.ListView> y un control <xref:System.Windows.Forms.TreeView> para mostrar la misma lista de archivos, al cambiar el icono de un archivo en la lista de imágenes hará que el nuevo icono aparezca en ambas vistas.

## <a name="using-imagelist-with-controls"></a>Usar ImageList con controles

Puede usar una lista de imágenes con cualquier control que tenga una propiedad `ImageList` o, en el caso del control <xref:System.Windows.Forms.ListView>, las propiedades <xref:System.Windows.Forms.ListView.SmallImageList%2A> y <xref:System.Windows.Forms.ListView.LargeImageList%2A>. Entre los controles que pueden asociarse con una lista de imágenes se incluyen <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.Label>. Para asociar la lista de imágenes con un control, establezca la propiedad `ImageList` del control en el nombre del componente <xref:System.Windows.Forms.ImageList>.

## <a name="key-properties"></a>Propiedades clave

La propiedad de clave del componente <xref:System.Windows.Forms.ImageList> es <xref:System.Windows.Forms.ImageList.Images%2A>, que contiene las imágenes que usará el control asociado. Puede acceder a cada imagen individual por su valor de índice o por su clave. La propiedad <xref:System.Windows.Forms.ImageList.ColorDepth%2A> determina el número de colores con los que se pueden representar las imágenes. Las imágenes se mostrarán con el mismo tamaño, establecido por la propiedad <xref:System.Windows.Forms.ImageList.ImageSize%2A>. El tamaño de las imágenes más grandes se ajustará.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ImageList>
- [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)