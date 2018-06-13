---
title: 'Cómo: Exponer propiedades de controles constituyentes'
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
ms.openlocfilehash: 8f7b5c44a5cb20b5da10df5fd630b371cc959fa8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532638"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Cómo: Exponer propiedades de controles constituyentes
Los controles que componen un control compuesto se denominan *controles constituyentes*. Estos controles normalmente se ha declarado privados y, por tanto, no es accesible para el desarrollador. Si desea disponer de propiedades de estos controles para futuros usuarios, debe exponer al usuario. Una propiedad de un control constituyente se expone mediante la creación de una propiedad en el control de usuario y usando la `get` y `set` descriptores de acceso de esa propiedad para llevar a cabo el cambio en la propiedad privada del control que lo componen.  
  
 Considere la posibilidad de un control de usuario hipotético con un botón constituyente denominado `MyButton`. En este ejemplo, cuando el usuario solicita la `ConstituentButtonBackColor` propiedad, el valor almacenado en el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` se entrega. Cuando el usuario asigna un valor a esta propiedad, ese valor se pasa automáticamente a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` y `set` el código se ejecutará, cambiar el color del `MyButton`.  
  
 En el ejemplo siguiente se muestra cómo exponer el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del botón constituyente:  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>Para exponer una propiedad de un control constituyente  
  
1.  Cree una propiedad pública para el control de usuario.  
  
2.  En la `get` sección de la propiedad, escriba código que recupera el valor de la propiedad que desea exponer.  
  
3.  En la `set` sección de la propiedad, escriba código que pasa el valor de la propiedad a la propiedad expuesta del control constituyente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.UserControl>  
 [Propiedades de los controles de Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
