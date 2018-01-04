---
title: Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 967b4a0e883338c756aceef37d11edecfb978527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
Controles en el cuadro de herramientas estándar de Windows Forms admiten muchas de las directrices de accesibilidad, incluida la exposición el foco del teclado y de los elementos de la pantalla.  
  
## <a name="planning-ahead-for-accessibility"></a>Planear con antelación para mejorar la accesibilidad  
 Propiedades de los controles se pueden utilizar para admitir otras directrices de accesibilidad, como se muestra en la tabla siguiente. Además, es recomendable utilizar menús para proporcionar acceso a características del programa.  
  
|Propiedad de control|Consideraciones para la accesibilidad|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La descripción se notifica a las ayudas de accesibilidad como lectores de pantalla. Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.|  
|AccessibleName|El nombre que se informará a las ayudas de accesibilidad.|  
|AccessibleRole|Describe el uso del elemento de la interfaz de usuario.|  
|TabIndex|Crea una ruta razonable para desplazarse a través del formulario. Es importante para los controles sin etiquetas intrínsecas, como cuadros de texto, para que sus etiquetas asociadas precedan inmediatamente a ellos en el orden de tabulación.|  
|Texto|Use el carácter "&" para crear teclas de acceso. Utilizando las teclas de acceso forma parte de proporcionar acceso mediante teclado documentado a las características.|  
|Tamaño de fuente|Si el tamaño de fuente no es ajustable, a continuación, se debe establecer en 10 puntos o más. Una vez que se establece el tamaño de fuente del formulario, todos los controles que se agregan posteriormente al formulario tendrán el mismo tamaño.|  
|Forecolor|Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.|  
|Backcolor|Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.|  
|BackgroundImage|Deje esta propiedad en blanco para mejorar la legibilidad del texto.|  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Crear una aplicación accesible basada en Windows](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
