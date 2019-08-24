---
title: Procedimiento para proporcionar un mapa de bits del cuadro de herramientas para un control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e6da7318ba481af721a9220c8f71af2a18e764a3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015784"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Procedimiento para proporcionar un mapa de bits del cuadro de herramientas para un control

Si desea que aparezca un icono especial para el control en el cuadro de **herramientas** de Visual Studio, puede especificar una imagen determinada mediante el <xref:System.Drawing.ToolboxBitmapAttribute>. Esta clase es un *atributo*, un tipo especial de clase que se puede asociar a otras clases. Para obtener más información sobre los atributos, vea [información general sobre los atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) para Visual Basic C#o [atributosC#()](../../../csharp/programming-guide/concepts/attributes/index.md) para.

<xref:System.Drawing.ToolboxBitmapAttribute>Con, puede especificar una cadena que indica la ruta de acceso y el nombre de archivo de un mapa de bits de 16 por 16 píxeles. Este mapa de bits aparecerá junto al control cuando se agregue al **cuadro de herramientas**. También puede especificar un <xref:System.Type>objeto, en cuyo caso se carga el mapa de bits asociado a ese tipo. Si especifica tanto un <xref:System.Type> como una cadena, el control busca un recurso de imagen con el nombre especificado por el parámetro de cadena en el ensamblado que contiene el tipo especificado por el <xref:System.Type> parámetro.

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Para especificar un mapa de bits del cuadro de herramientas para el control

1. Agregue a la declaración de clase del control antes de la `Class` palabra clave para Visual Basic y por encima de la declaración de clase para visual. C# <xref:System.Drawing.ToolboxBitmapAttribute>

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. Recompile el proyecto.

    > [!NOTE]
    > El mapa de bits no aparece en el cuadro de herramientas para componentes y controles generados automáticamente. Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**. Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)herramientas con componentes personalizados.

## <a name="see-also"></a>Vea también

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
- [Información general sobre los atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Atributos (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
