---
title: Usar varianza en delegados (C#)
description: Aprenda a usar la varianza en delegados con los ejemplos de código de covarianza y contravarianza incluidos.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 6704c3bf09dd854335f1e2719ccc8462cb7cde26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176323"
---
# <a name="using-variance-in-delegates-c"></a>Usar varianza en delegados (C#)

Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método. La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado. La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.  
  
## <a name="example-1-covariance"></a>Ejemplo 1: Covarianza  
  
### <a name="description"></a>Descripción  

 En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado. El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.  
  
### <a name="code"></a>Código  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a>Ejemplo 2: Contravarianza  
  
### <a name="description"></a>Descripción

En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros que son tipos base del tipo de parámetro de la firma del delegado. Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes. En el ejemplo siguiente se usan dos delegados:

- Un delegado <xref:System.Windows.Forms.KeyEventHandler> que define la firma del evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown). Su firma es:

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- Un delegado <xref:System.Windows.Forms.MouseEventHandler> que define la firma del evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown). Su firma es:

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

En el ejemplo se define un controlador de eventos con un parámetro <xref:System.EventArgs>, que se usa para controlar los eventos `Button.KeyDown` y `Button.MouseClick`. Es posible hacer esto porque <xref:System.EventArgs> es un tipo base de <xref:System.Windows.Forms.KeyEventArgs> y <xref:System.Windows.Forms.MouseEventArgs>.
  
### <a name="code"></a>Código  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Varianza en delegados (C#)](./variance-in-delegates.md)
- [Usar varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
