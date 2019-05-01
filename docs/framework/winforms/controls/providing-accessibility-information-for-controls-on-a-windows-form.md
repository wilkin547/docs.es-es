---
title: Proporcionar información de accesibilidad de controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 0f589f37d79c9ec8d55153aac4c846726a379055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948027"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>Proporcionar información de accesibilidad de controles en Windows Forms
Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz. Algunos ejemplos son los lectores de pantalla para invidentes y las utilidades de entrada de voz para las personas que usan comandos verbales en lugar del mouse o el teclado. Estas ayudas de accesibilidad interactúan con las propiedades de accesibilidad que exponen los controles de Windows Forms. Dichas propiedades son:  
  
- **AccessibilityObject**  
  
- **AccessibleDefaultActionDescription**  
  
- **AccessibleDescription**  
  
- **AccessibleName**  
  
- **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>AccessibilityObject Property  
 Esta propiedad de solo lectura contiene una instancia de la <xref:System.Windows.Forms.AccessibleObject> . La propiedad **AccessibleObject** implementa la interfaz de <xref:Accessibility.IAccessible> , que proporciona información acerca de la descripción, la ubicación de la pantalla, las funciones de desplazamiento y valor del control. El diseñador establece este valor cuando se agrega el control al formulario.  
  
## <a name="accessibledefaultactiondescription-property"></a>Propiedad AccessibleDefaultActionDescription  
 Esta cadena describe la acción del control. No aparece en la ventana Propiedades y es posible que solo se establezca en el código. Los ejemplos siguientes establecen esta propiedad para un control de botón:  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>Propiedad AccessibleDescription  
 Esta cadena describe el control. Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>Propiedad AccessibleName  
 Este es el nombre de un control notificado a las ayudas de accesibilidad. Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>Propiedad AccessibleRole  
 Esta propiedad, que contiene una <xref:System.Windows.Forms.AccessibleRole> , describe el rol de la interfaz de usuario del control. Un nuevo control tiene el valor establecido en `Default`. Esto significa que, de forma predeterminada, un control **Button** actúa como un **Button**. Es posible que quiera restablecer esta propiedad si un control tiene otro rol. Por ejemplo, puede que esté usando un control **PictureBox** como un control **Chart**y quiera que las ayudas de accesibilidad informen del rol como **Chart**y no como **PictureBox**. Es posible que también quiera especificar esta propiedad para los controles personalizados que ha desarrollado. Esta propiedad se puede establecer en la ventana Propiedades o en el código de la manera siguiente:  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
