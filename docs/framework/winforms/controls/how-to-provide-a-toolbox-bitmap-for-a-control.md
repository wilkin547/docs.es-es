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
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="72c64-102">Procedimiento para proporcionar un mapa de bits del cuadro de herramientas para un control</span><span class="sxs-lookup"><span data-stu-id="72c64-102">How to: Provide a Toolbox Bitmap for a Control</span></span>

<span data-ttu-id="72c64-103">Si desea que aparezca un icono especial para el control en el cuadro de **herramientas** de Visual Studio, puede especificar una imagen determinada mediante el <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="72c64-103">If you want to have a special icon for your control appear in the **Toolbox** of Visual Studio, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="72c64-104">Esta clase es un *atributo*, un tipo especial de clase que se puede asociar a otras clases.</span><span class="sxs-lookup"><span data-stu-id="72c64-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="72c64-105">Para obtener más información sobre los atributos, vea [información general sobre los atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) para Visual Basic C#o [atributosC#()](../../../csharp/programming-guide/concepts/attributes/index.md) para.</span><span class="sxs-lookup"><span data-stu-id="72c64-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>

<span data-ttu-id="72c64-106"><xref:System.Drawing.ToolboxBitmapAttribute>Con, puede especificar una cadena que indica la ruta de acceso y el nombre de archivo de un mapa de bits de 16 por 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="72c64-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="72c64-107">Este mapa de bits aparecerá junto al control cuando se agregue al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="72c64-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="72c64-108">También puede especificar un <xref:System.Type>objeto, en cuyo caso se carga el mapa de bits asociado a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="72c64-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="72c64-109">Si especifica tanto un <xref:System.Type> como una cadena, el control busca un recurso de imagen con el nombre especificado por el parámetro de cadena en el ensamblado que contiene el tipo especificado por el <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="72c64-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="72c64-110">Para especificar un mapa de bits del cuadro de herramientas para el control</span><span class="sxs-lookup"><span data-stu-id="72c64-110">To specify a Toolbox bitmap for your control</span></span>

1. <span data-ttu-id="72c64-111">Agregue a la declaración de clase del control antes de la `Class` palabra clave para Visual Basic y por encima de la declaración de clase para visual. C# <xref:System.Drawing.ToolboxBitmapAttribute></span><span class="sxs-lookup"><span data-stu-id="72c64-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>

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

2. <span data-ttu-id="72c64-112">Recompile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="72c64-112">Rebuild the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="72c64-113">El mapa de bits no aparece en el cuadro de herramientas para componentes y controles generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="72c64-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="72c64-114">Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="72c64-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="72c64-115">Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)herramientas con componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="72c64-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72c64-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="72c64-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="72c64-117">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="72c64-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="72c64-118">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="72c64-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="72c64-119">Información general sobre los atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72c64-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="72c64-120">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="72c64-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
