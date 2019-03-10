---
title: Filtrar Proporcionar un mapa de bits del cuadro de herramientas para un Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 9072f96bd6e3485e759ed72819229b3f0c33d641
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715963"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="846e4-102">Procedimiento Proporcionar un mapa de bits del cuadro de herramientas para un Control</span><span class="sxs-lookup"><span data-stu-id="846e4-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="846e4-103">Si desea tener un icono especial para el control aparezca en el **cuadro de herramientas**, puede especificar una imagen determinada mediante el <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="846e4-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="846e4-104">Esta clase es un *atributo*, un tipo especial de clase que se puede asociar a otras clases.</span><span class="sxs-lookup"><span data-stu-id="846e4-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="846e4-105">Para obtener más información acerca de los atributos, vea [información general de atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) para Visual Basic o [atributos (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) para C#.</span><span class="sxs-lookup"><span data-stu-id="846e4-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>  
  
 <span data-ttu-id="846e4-106">Mediante el <xref:System.Drawing.ToolboxBitmapAttribute>, puede especificar una cadena que indica la ruta de acceso y nombre de archivo para un mapa de bits de 16 por 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="846e4-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="846e4-107">Este mapa de bits aparecerá junto al control cuando se agregue al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="846e4-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="846e4-108">También puede especificar un <xref:System.Type>, en cuyo caso se carga el mapa de bits asociado con ese tipo.</span><span class="sxs-lookup"><span data-stu-id="846e4-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="846e4-109">Si especifica tanto un <xref:System.Type> y una cadena, el control busca un recurso de imagen con el nombre especificado por el parámetro de cadena en el ensamblado que contiene el tipo especificado por el <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="846e4-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="846e4-110">Para especificar un mapa de bits del cuadro de herramientas para el control</span><span class="sxs-lookup"><span data-stu-id="846e4-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="846e4-111">Agregar el <xref:System.Drawing.ToolboxBitmapAttribute> a la declaración de clase del control antes de la `Class` palabra clave de visual Basic y sobre la declaración de clase de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="846e4-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
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
  
2.  <span data-ttu-id="846e4-112">Recompile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="846e4-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="846e4-113">El mapa de bits no aparece en el cuadro de herramientas para componentes y controles generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="846e4-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="846e4-114">Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="846e4-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="846e4-115">Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="846e4-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846e4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="846e4-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="846e4-117">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="846e4-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="846e4-118">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="846e4-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="846e4-119">Información general sobre los atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="846e4-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="846e4-120">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="846e4-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
