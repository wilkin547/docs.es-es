---
title: Procedimiento para exponer propiedades de controles constituyentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015879"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="c947a-102">Procedimiento para exponer propiedades de controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="c947a-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="c947a-103">Los controles que componen un control compuesto se denominan *controles constituyentes*.</span><span class="sxs-lookup"><span data-stu-id="c947a-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="c947a-104">Estos controles se declaran normalmente como privados y, por lo tanto, el desarrollador no puede acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="c947a-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="c947a-105">Si desea que las propiedades de estos controles estén disponibles para los usuarios futuros, debe exponerlos al usuario.</span><span class="sxs-lookup"><span data-stu-id="c947a-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="c947a-106">Una propiedad de un control constituyente se expone mediante la creación de una propiedad en el control de usuario y `get` el `set` uso de los descriptores de acceso y de esa propiedad para aplicar el cambio en la propiedad privada del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="c947a-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="c947a-107">Considere un control de usuario hipotético con un botón constituyente `MyButton`denominado.</span><span class="sxs-lookup"><span data-stu-id="c947a-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="c947a-108">En este ejemplo, cuando el usuario solicita la `ConstituentButtonBackColor` propiedad, se entrega el valor almacenado <xref:System.Windows.Forms.Control.BackColor%2A> en la `MyButton` propiedad de.</span><span class="sxs-lookup"><span data-stu-id="c947a-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="c947a-109">Cuando el usuario asigna un valor a esta propiedad, ese valor se pasa <xref:System.Windows.Forms.Control.BackColor%2A> automáticamente a la propiedad de `MyButton` y se ejecuta el `set` código, cambiando el color de. `MyButton`</span><span class="sxs-lookup"><span data-stu-id="c947a-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="c947a-110">En el ejemplo siguiente se muestra cómo exponer <xref:System.Windows.Forms.Control.BackColor%2A> la propiedad del botón constituyente:</span><span class="sxs-lookup"><span data-stu-id="c947a-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

```vb
Public Property ButtonColor() as System.Drawing.Color
   Get
      Return MyButton.BackColor
   End Get
   Set(Value as System.Drawing.Color)
      MyButton.BackColor = Value
   End Set
End Property
```

```csharp
public Color ButtonColor
{
   get
   {
      return(myButton.BackColor);
   }
   set
   {
      myButton.BackColor = value;
   }
}
```

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="c947a-111">Para exponer una propiedad de un control constituyente</span><span class="sxs-lookup"><span data-stu-id="c947a-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="c947a-112">Cree una propiedad pública para el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="c947a-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="c947a-113">En la `get` sección de la propiedad, escriba el código que recupera el valor de la propiedad que desea exponer.</span><span class="sxs-lookup"><span data-stu-id="c947a-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="c947a-114">En la `set` sección de la propiedad, escriba código que pase el valor de la propiedad a la propiedad expuesta del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="c947a-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="c947a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c947a-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="c947a-116">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c947a-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="c947a-117">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="c947a-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
