---
title: Filtrar Cambiar el tamaño de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 9399069ad5365b025fe8c92b2f10c36c4666f4b4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705429"
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="986fe-102">Filtrar Cambiar el tamaño de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="986fe-102">How to: Resize Windows Forms</span></span>
<span data-ttu-id="986fe-103">Puede especificar el tamaño de su Windows Form de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="986fe-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="986fe-104">Puede cambiar el alto y el ancho del formulario mediante programación estableciendo un nuevo valor para la propiedad <xref:System.Windows.Forms.Form.Size%2A>, o ajustar las propiedades <xref:System.Windows.Forms.Control.Height%2A> o <xref:System.Windows.Forms.Control.Width%2A> individualmente.</span><span class="sxs-lookup"><span data-stu-id="986fe-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="986fe-105">Si utiliza Visual Studio, puede cambiar el tamaño mediante el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="986fe-105">If you are using Visual Studio, you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="986fe-106">Consulte también [Cómo: Cambiar el tamaño mediante el Diseñador de formularios de Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="986fe-106">Also see [How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span></span>  
  
### <a name="to-resize-a-form-programmatically"></a><span data-ttu-id="986fe-107">Para cambiar el tamaño de un formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="986fe-107">To resize a form programmatically</span></span>  
  
-   <span data-ttu-id="986fe-108">Para definir el tamaño de un formulario en tiempo de ejecución, establezca la propiedad <xref:System.Windows.Forms.Form.Size%2A> del formulario.</span><span class="sxs-lookup"><span data-stu-id="986fe-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>  
  
     <span data-ttu-id="986fe-109">En el ejemplo de código siguiente se muestra el tamaño del formulario establecido en 100 x 100 píxeles.</span><span class="sxs-lookup"><span data-stu-id="986fe-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a><span data-ttu-id="986fe-110">Para cambiar el alto y ancho del formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="986fe-110">To change form width and height programmatically</span></span>  
  
-   <span data-ttu-id="986fe-111">Después de definir <xref:System.Windows.Forms.Form.Size%2A>, cambie el alto o el ancho del formulario usando las propiedades <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="986fe-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="986fe-112">En el ejemplo de código siguiente se muestra el ancho del formulario establecido en 300 píxeles desde el borde izquierdo del formulario, mientras que el alto permanece constante.</span><span class="sxs-lookup"><span data-stu-id="986fe-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     <span data-ttu-id="986fe-113">O bien</span><span class="sxs-lookup"><span data-stu-id="986fe-113">-or-</span></span>  
  
     <span data-ttu-id="986fe-114">Cambie <xref:System.Drawing.Size.Width%2A> o <xref:System.Drawing.Size.Height%2A> estableciendo la propiedad <xref:System.Windows.Forms.Form.Size%2A>.</span><span class="sxs-lookup"><span data-stu-id="986fe-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>  
  
     <span data-ttu-id="986fe-115">Sin embargo, tal y como se muestra en el ejemplo de código siguiente, este enfoque es más complejo que simplemente establecer las propiedades <xref:System.Windows.Forms.Control.Width%2A> o <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="986fe-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a><span data-ttu-id="986fe-116">Para cambiar el tamaño del formulario por incrementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="986fe-116">To change form size by increments programmatically</span></span>  
  
-   <span data-ttu-id="986fe-117">Para incrementar el tamaño del formulario, establezca las propiedades <xref:System.Drawing.Size.Width%2A> y <xref:System.Drawing.Size.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="986fe-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="986fe-118">En el ejemplo de código siguiente se muestra el ancho del formulario establecido en 200 píxeles más que la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="986fe-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="986fe-119">Use siempre la propiedad <xref:System.Drawing.Size.Height%2A> o <xref:System.Drawing.Size.Width%2A> para cambiar una dimensión de un formulario, a menos que quiera establecer las dimensiones de alto y ancho al mismo tiempo estableciendo la propiedad <xref:System.Windows.Forms.Form.Size%2A> en una nueva estructura <xref:System.Drawing.Size>.</span><span class="sxs-lookup"><span data-stu-id="986fe-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="986fe-120">La propiedad <xref:System.Windows.Forms.Form.Size%2A> devuelve una estructura <xref:System.Drawing.Size>, que es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="986fe-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="986fe-121">No se puede asignar un nuevo valor a la propiedad de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="986fe-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="986fe-122">Por lo tanto, el ejemplo de código siguiente no se compilará.</span><span class="sxs-lookup"><span data-stu-id="986fe-122">Therefore, the following code example will not compile.</span></span>  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="986fe-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="986fe-123">See also</span></span>
- [<span data-ttu-id="986fe-124">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="986fe-124">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="986fe-125">Mejorar las aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="986fe-125">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
