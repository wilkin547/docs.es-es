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
# <a name="how-to-expose-properties-of-constituent-controls"></a>Procedimiento para exponer propiedades de controles constituyentes
Los controles que componen un control compuesto se denominan *controles constituyentes*. Estos controles se declaran normalmente como privados y, por lo tanto, el desarrollador no puede acceder a ellos. Si desea que las propiedades de estos controles estén disponibles para los usuarios futuros, debe exponerlos al usuario. Una propiedad de un control constituyente se expone mediante la creación de una propiedad en el control de usuario y `get` el `set` uso de los descriptores de acceso y de esa propiedad para aplicar el cambio en la propiedad privada del control constituyente.

 Considere un control de usuario hipotético con un botón constituyente `MyButton`denominado. En este ejemplo, cuando el usuario solicita la `ConstituentButtonBackColor` propiedad, se entrega el valor almacenado <xref:System.Windows.Forms.Control.BackColor%2A> en la `MyButton` propiedad de. Cuando el usuario asigna un valor a esta propiedad, ese valor se pasa <xref:System.Windows.Forms.Control.BackColor%2A> automáticamente a la propiedad de `MyButton` y se ejecuta el `set` código, cambiando el color de. `MyButton`

 En el ejemplo siguiente se muestra cómo exponer <xref:System.Windows.Forms.Control.BackColor%2A> la propiedad del botón constituyente:

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

2. En la `get` sección de la propiedad, escriba el código que recupera el valor de la propiedad que desea exponer.

3. En la `set` sección de la propiedad, escriba código que pase el valor de la propiedad a la propiedad expuesta del control constituyente.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
