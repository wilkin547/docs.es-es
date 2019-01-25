---
title: Procedimiento Exponer propiedades de controles constituyentes
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
ms.openlocfilehash: f3ad37032ee2bb85f37a0eb754277cc9bc040a38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532167"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="07df5-102">Procedimiento Exponer propiedades de controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="07df5-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="07df5-103">Los controles que componen un control compuesto se denominan *controles constituyentes*.</span><span class="sxs-lookup"><span data-stu-id="07df5-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="07df5-104">Estos controles suelen declararse como privados y, por tanto, no se puede acceder por el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="07df5-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="07df5-105">Si desea que las propiedades de estos controles disponibles para usuarios futuros, debe exponer al usuario.</span><span class="sxs-lookup"><span data-stu-id="07df5-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="07df5-106">Se expone una propiedad de un control constituyente creando una propiedad en el control de usuario, y usando el `get` y `set` descriptores de acceso de esa propiedad para llevar a cabo el cambio en la propiedad privada del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="07df5-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="07df5-107">Considere la posibilidad de un control de usuario hipotético con un botón constituyente denominado `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="07df5-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="07df5-108">En este ejemplo, cuando el usuario solicita la `ConstituentButtonBackColor` propiedad, el valor almacenado en el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` se entrega.</span><span class="sxs-lookup"><span data-stu-id="07df5-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="07df5-109">Cuando el usuario asigna un valor a esta propiedad, ese valor se pasa automáticamente a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` y `set` se ejecutará el código, cambiar el color de `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="07df5-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="07df5-110">El ejemplo siguiente muestra cómo exponer la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del botón constituyente:</span><span class="sxs-lookup"><span data-stu-id="07df5-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="07df5-111">Para exponer una propiedad de un control constituyente</span><span class="sxs-lookup"><span data-stu-id="07df5-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="07df5-112">Cree una propiedad pública para el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="07df5-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="07df5-113">En la `get` sección de la propiedad, escribir código que recupera el valor de la propiedad que desea exponer.</span><span class="sxs-lookup"><span data-stu-id="07df5-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="07df5-114">En la `set` sección de la propiedad, escribir código que pasa el valor de la propiedad a la propiedad expuesta del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="07df5-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07df5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="07df5-115">See also</span></span>
- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="07df5-116">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07df5-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [<span data-ttu-id="07df5-117">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="07df5-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
