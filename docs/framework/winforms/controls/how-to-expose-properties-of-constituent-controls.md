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
ms.openlocfilehash: 44b96218e674c754a1985f2f22a36707cd1776b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294917"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Procedimiento para exponer propiedades de controles constituyentes
Los controles que componen un control compuesto se denominan *controles constituyentes*. Estos controles suelen declararse como privados y, por tanto, no se puede acceder por el desarrollador. Si desea que las propiedades de estos controles disponibles para usuarios futuros, debe exponer al usuario. Se expone una propiedad de un control constituyente creando una propiedad en el control de usuario, y usando el `get` y `set` descriptores de acceso de esa propiedad para llevar a cabo el cambio en la propiedad privada del control constituyente.  
  
 Considere la posibilidad de un control de usuario hipotético con un botón constituyente denominado `MyButton`. En este ejemplo, cuando el usuario solicita la `ConstituentButtonBackColor` propiedad, el valor almacenado en el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` se entrega. Cuando el usuario asigna un valor a esta propiedad, ese valor se pasa automáticamente a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad de `MyButton` y `set` se ejecutará el código, cambiar el color de `MyButton`.  
  
 El ejemplo siguiente muestra cómo exponer la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del botón constituyente:  
  
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
  
1. Cree una propiedad pública para el control de usuario.  
  
2. En la `get` sección de la propiedad, escribir código que recupera el valor de la propiedad que desea exponer.  
  
3. En la `set` sección de la propiedad, escribir código que pasa el valor de la propiedad a la propiedad expuesta del control constituyente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
