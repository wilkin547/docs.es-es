---
title: Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b731f277620925a333c8d9eba64c8900674327da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552221"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
Los controles en el cuadro de herramientas estándar de Windows Forms admiten muchas de las directrices de accesibilidad, incluida la exposición del foco del teclado y exponer los elementos de la pantalla.  
  
## <a name="planning-ahead-for-accessibility"></a>Planear para mejorar la accesibilidad  
 Propiedades de los controles pueden usarse para admitir otras directrices de accesibilidad, como se muestra en la tabla siguiente. Además, debe usar los menús para proporcionar acceso a las características del programa.  
  
|Propiedad de control|Consideraciones para la accesibilidad|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La descripción se notifica a las ayudas de accesibilidad como lectores de pantalla. Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.|  
|AccessibleName|El nombre que se notificará a las ayudas de accesibilidad.|  
|AccessibleRole|Describe el uso del elemento en la interfaz de usuario.|  
|TabIndex|Crea una ruta de navegación razonable a través del formulario. Es importante para los controles sin etiquetas intrínsecas, como cuadros de texto, para que sus etiquetas asociadas preceda inmediatamente en el orden de tabulación.|  
|Texto|Use el carácter "&" para crear teclas de acceso. Utilizando las teclas de acceso forma parte de proporcionar acceso mediante teclado documentado a las características.|  
|Tamaño de fuente|Si el tamaño de fuente no es ajustable, a continuación, se debe establecer en 10 puntos o más. Una vez que se establece el tamaño de fuente del formulario, todos los controles que se agregan posteriormente al formulario tendrán el mismo tamaño.|  
|Forecolor|Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.|  
|Backcolor|Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.|  
|BackgroundImage|Deje esta propiedad en blanco para que el texto sea más legible.|  
  
## <a name="see-also"></a>Vea también
- [Tutorial: Crear una aplicación accesible basada en Windows](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
