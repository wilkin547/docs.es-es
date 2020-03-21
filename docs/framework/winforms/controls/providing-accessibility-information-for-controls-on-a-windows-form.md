---
title: Proporcionar información de accesibilidad de controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181995"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>Proporcionar información de accesibilidad de controles en Windows Forms
Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz. Algunos ejemplos son los lectores de pantalla para invidentes y las utilidades de entrada de voz para las personas que usan comandos verbales en lugar del mouse o el teclado. Estas ayudas de accesibilidad interactúan con las propiedades de accesibilidad que exponen los controles de Windows Forms. Estas propiedades son:  
  
- **AccessibilityObject**  
  
- **AccessibleDefaultActionDescription**  
  
- **AccessibleDescription**  
  
- **AccessibleName**  
  
- **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>AccessibilityObject Property  
 Esta propiedad de solo lectura contiene una instancia de la <xref:System.Windows.Forms.AccessibleObject> . La propiedad **AccessibleObject** implementa la interfaz de <xref:Accessibility.IAccessible> , que proporciona información acerca de la descripción, la ubicación de la pantalla, las funciones de desplazamiento y valor del control. El diseñador establece este valor cuando se agrega el control al formulario.  
  
## <a name="accessibledefaultactiondescription-property"></a>Propiedad AccessibleDefaultActionDescription  
 Esta cadena describe la acción del control. No aparece en la ventana Propiedades y es posible que solo se establezca en el código. Los ejemplos siguientes establecen esta propiedad para un control de botón:  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>Propiedad AccessibleDescription  
 Esta cadena describe el control. Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>Propiedad AccessibleName  
 Este es el nombre de un control notificado a las ayudas de accesibilidad. Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>Propiedad AccessibleRole  
 Esta propiedad, que contiene una <xref:System.Windows.Forms.AccessibleRole> , describe el rol de la interfaz de usuario del control. Un nuevo control tiene el valor establecido en `Default`. Esto significa que, de forma predeterminada, un control **Button** actúa como un **Button**. Es posible que quiera restablecer esta propiedad si un control tiene otro rol. Por ejemplo, puede que esté usando un control **PictureBox** como un control **Chart**y quiera que las ayudas de accesibilidad informen del rol como **Chart**y no como **PictureBox**. Es posible que también quiera especificar esta propiedad para los controles personalizados que ha desarrollado. Esta propiedad se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
