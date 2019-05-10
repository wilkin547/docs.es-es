---
title: Definir valores predeterminados con los métodos ShouldSerialize y Reset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 5c95272c672d9b35d61e2fca8cccdbc532ef6776
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211302"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="6bbce-102">Definir valores predeterminados con los métodos ShouldSerialize y Reset</span><span class="sxs-lookup"><span data-stu-id="6bbce-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="6bbce-103">`ShouldSerialize` y `Reset` son métodos opcionales que puede proporcionar para una propiedad, si la propiedad no es un valor predeterminado simple.</span><span class="sxs-lookup"><span data-stu-id="6bbce-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="6bbce-104">Si la propiedad tiene un valor predeterminado simple, debe aplicar el <xref:System.ComponentModel.DefaultValueAttribute> y proporcionar el valor predeterminado para el constructor de clase de atributo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6bbce-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="6bbce-105">Cualquiera de estos mecanismos habilita las siguientes características en el diseñador:</span><span class="sxs-lookup"><span data-stu-id="6bbce-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="6bbce-106">La propiedad proporciona una indicación visual en el Explorador de propiedades si se ha modificado desde su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6bbce-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="6bbce-107">El usuario puede hacer doble clic en la propiedad y elija **restablecer** para restaurar la propiedad a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6bbce-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="6bbce-108">El diseñador genera código más eficaz.</span><span class="sxs-lookup"><span data-stu-id="6bbce-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="6bbce-109">Se aplica ya sea el <xref:System.ComponentModel.DefaultValueAttribute> o proporcionar `Reset` *PropertyName* y `ShouldSerialize` *PropertyName* métodos.</span><span class="sxs-lookup"><span data-stu-id="6bbce-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="6bbce-110">No use ambos.</span><span class="sxs-lookup"><span data-stu-id="6bbce-110">Do not use both.</span></span>

 <span data-ttu-id="6bbce-111">El `Reset` *PropertyName* método establece una propiedad en su valor predeterminado, tal como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="6bbce-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

```vb
Public Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
public void ResetMyFont() {
   MyFont = null;
}
```

> [!NOTE]
>  <span data-ttu-id="6bbce-112">Si no tiene una propiedad de un `Reset` método, no está marcado con un <xref:System.ComponentModel.DefaultValueAttribute>y no tiene un valor predeterminado en su declaración, el `Reset` opción para esa propiedad está deshabilitada en el menú contextual de la **propiedades** ventana del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6bbce-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="6bbce-113">Los diseñadores como Visual Studio usan el `ShouldSerialize` *PropertyName* se cambia el método para comprobar si una propiedad ha cambiado desde su valor predeterminado y escribir código en el solo si forma una propiedad, lo que permite para un código más eficaz generación.</span><span class="sxs-lookup"><span data-stu-id="6bbce-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="6bbce-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bbce-114">For example:</span></span>

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Public Function ShouldSerializeMyFont() As Boolean
   Return Not (thefont Is Nothing)
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
public bool ShouldSerializeMyFont() {
   return thefont != null;
}
```

 <span data-ttu-id="6bbce-115">Sigue un ejemplo de código completo.</span><span class="sxs-lookup"><span data-stu-id="6bbce-115">A complete code example follows.</span></span>

```vb
Option Explicit
Option Strict

Imports System
Imports System.Windows.Forms
Imports System.Drawing

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Public Function ShouldSerializeMyFont() As Boolean
      Return Not (thefont Is Nothing)
   End Function

   Public Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Drawing;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   public bool ShouldSerializeMyFont() {
      return thefont != null;
   }

   public void ResetMyFont() {
      MyFont = null;
   }
}
```

 <span data-ttu-id="6bbce-116">En este caso, incluso cuando el valor de la variable privada obtiene acceso a la `MyFont` propiedad es `null`, no se muestra el Explorador de propiedades `null`; en su lugar, muestra el <xref:System.Windows.Forms.Control.Font%2A> propiedad del elemento primario, si no es `null`, o el valor predeterminado <xref:System.Windows.Forms.Control.Font%2A> valor definido en <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="6bbce-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="6bbce-117">Por lo tanto, el valor predeterminado de `MyFont` no se puede establecer simplemente y un <xref:System.ComponentModel.DefaultValueAttribute> no se puede aplicar a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bbce-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="6bbce-118">En su lugar, el `ShouldSerialize` y `Reset` se deben implementar los métodos para la `MyFont` propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bbce-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bbce-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bbce-119">See also</span></span>

- [<span data-ttu-id="6bbce-120">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bbce-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="6bbce-121">Definir una propiedad</span><span class="sxs-lookup"><span data-stu-id="6bbce-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="6bbce-122">Eventos de cambio de propiedades</span><span class="sxs-lookup"><span data-stu-id="6bbce-122">Property-Changed Events</span></span>](property-changed-events.md)
