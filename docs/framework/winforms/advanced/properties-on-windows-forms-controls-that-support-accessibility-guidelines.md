---
title: Propiedades de accesibilidad en los controles
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743425"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
Los controles del cuadro de herramientas estándar para Windows Forms admiten muchas de las instrucciones de accesibilidad, incluida la exposición del foco del teclado y la exposición de los elementos de la pantalla.  
  
## <a name="planning-ahead-for-accessibility"></a>Planeación de accesibilidad  
 Las propiedades de los controles se pueden usar para admitir otras directrices de accesibilidad, como se muestra en la tabla siguiente. Además, debe usar menús para proporcionar acceso a las características del programa.  
  
|Propiedad de control|Consideraciones para la accesibilidad|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La descripción se muestra en ayudas de accesibilidad, como lectores de pantalla. Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.|  
|AccessibleName|El nombre que se inscribirá en las ayudas de accesibilidad.|  
|AccessibleRole|Describe el uso del elemento en la interfaz de usuario.|  
|TabIndex|Crea una ruta de navegación sensata a través del formulario. Es importante que los controles sin etiquetas intrínsecas, como los cuadros de texto, tengan su etiqueta asociada inmediatamente delante en el orden de tabulación.|  
|Text|Use el carácter "&" para crear teclas de acceso. El uso de las teclas de acceso forma parte de proporcionar acceso de teclado documentado a las características de.|  
|Tamaño de fuente|Si el tamaño de fuente no es ajustable, debe establecerse en 10 puntos o más. Una vez establecido el tamaño de fuente del formulario, a partir de ese momento, todos los controles agregados al formulario tendrán el mismo tamaño.|  
|Forecolor|Si esta propiedad se establece en el valor predeterminado, se usarán las preferencias de color del usuario en el formulario.|  
|Backcolor|Si esta propiedad se establece en el valor predeterminado, se usarán las preferencias de color del usuario en el formulario.|  
|BackgroundImage|Deje esta propiedad en blanco para que el texto sea más legible.|  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Crear una aplicación accesible basada en Windows](walkthrough-creating-an-accessible-windows-based-application.md)
